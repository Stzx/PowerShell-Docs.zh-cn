---
ms.date: 09/13/2016
ms.topic: reference
title: 使用 Windows PowerShell API 安排作业
description: 使用 Windows PowerShell API 安排作业
ms.openlocfilehash: c42b3ea311a5db4dcb6e11bb587f01f3deefe49b
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92647146"
---
# <a name="scheduling-jobs-with-the-windows-powershell-api"></a><span data-ttu-id="625f5-103">使用 Windows PowerShell API 安排作业</span><span class="sxs-lookup"><span data-stu-id="625f5-103">Scheduling Jobs with the Windows PowerShell API</span></span>

<span data-ttu-id="625f5-104">你可以使用由 N:Microsoft.PowerShell.ScheduledJob 命名空间公开的对象创建计划作业，定义其运行时间，并在运行作业后获取有关该作业的结果。</span><span class="sxs-lookup"><span data-stu-id="625f5-104">You can use the objects exposed by the N:Microsoft.PowerShell.ScheduledJob namespace to create a scheduled job, define when it runs, and get results about the completed job after it has run.</span></span>

## <a name="triggering-the-job"></a><span data-ttu-id="625f5-105">触发作业</span><span class="sxs-lookup"><span data-stu-id="625f5-105">Triggering the Job</span></span>

<span data-ttu-id="625f5-106">创建计划作业的第一步是指定作业应运行的时间。</span><span class="sxs-lookup"><span data-stu-id="625f5-106">The first step in creating a scheduled job is specifying when the job should run.</span></span> <span data-ttu-id="625f5-107">通过创建和配置 T:Microsoft.PowerShell.ScheduledJob.ScheduledJobTrigger 对象来实现此目的。</span><span class="sxs-lookup"><span data-stu-id="625f5-107">Do this by creating and configuring a T:Microsoft.PowerShell.ScheduledJob.ScheduledJobTrigger object.</span></span> <span data-ttu-id="625f5-108">下面的代码创建一个触发器，该触发器计划作业在未来20秒运行一次。</span><span class="sxs-lookup"><span data-stu-id="625f5-108">The following code creates a trigger that schedules a job to run a single time 20 seconds in the future.</span></span>

```csharp
ScheduledJobTrigger jobTrigger = ScheduledJobTrigger.CreateOnceTrigger(
    DateTime.Now.AddSeconds(20),        // Create trigger to start job 20 seconds after now.
    TimeSpan.Zero,                      // No random delay
    null,                               // No repetition interval time
    null,                               // No repetition interval duration
    1,                                  // Trigger Id
    true);                              // Create trigger enabled
```

## <a name="defining-the-job"></a><span data-ttu-id="625f5-109">定义作业</span><span class="sxs-lookup"><span data-stu-id="625f5-109">Defining the Job</span></span>

<span data-ttu-id="625f5-110">可以通过创建参数字典来定义 Windows PowerShell 作业。</span><span class="sxs-lookup"><span data-stu-id="625f5-110">You define a Windows PowerShell job by creating a parameter dictionary.</span></span> <span data-ttu-id="625f5-111">支持以下参数。</span><span class="sxs-lookup"><span data-stu-id="625f5-111">The following parameters are supported.</span></span>

|<span data-ttu-id="625f5-112">参数名称</span><span class="sxs-lookup"><span data-stu-id="625f5-112">Parameter Name</span></span>|<span data-ttu-id="625f5-113">描述</span><span class="sxs-lookup"><span data-stu-id="625f5-113">Description</span></span>|
|---|---|
|<span data-ttu-id="625f5-114">名称</span><span class="sxs-lookup"><span data-stu-id="625f5-114">Name</span></span>|<span data-ttu-id="625f5-115">作业的名称。</span><span class="sxs-lookup"><span data-stu-id="625f5-115">The name of the job.</span></span>|
|<span data-ttu-id="625f5-116">ScriptBock</span><span class="sxs-lookup"><span data-stu-id="625f5-116">ScriptBock</span></span>|<span data-ttu-id="625f5-117">指定作业执行的操作的 Windows PowerShell 脚本块。</span><span class="sxs-lookup"><span data-stu-id="625f5-117">A Windows PowerShell script block that specifies what the job does.</span></span>|
|<span data-ttu-id="625f5-118">文件路径</span><span class="sxs-lookup"><span data-stu-id="625f5-118">FilePath</span></span>|<span data-ttu-id="625f5-119">文件的路径，该文件包含用于指定作业执行的操作的 Windows PowerShell 脚本块。</span><span class="sxs-lookup"><span data-stu-id="625f5-119">A path to a file that contains Windows PowerShell script block that specifies what the job does.</span></span>|
|<span data-ttu-id="625f5-120">InitializationScript</span><span class="sxs-lookup"><span data-stu-id="625f5-120">InitializationScript</span></span>|<span data-ttu-id="625f5-121">用于初始化作业的 Windows PowerShell 脚本块。</span><span class="sxs-lookup"><span data-stu-id="625f5-121">A Windows PowerShell script block that initializes the job.</span></span>|
|<span data-ttu-id="625f5-122">ArgumentList</span><span class="sxs-lookup"><span data-stu-id="625f5-122">ArgumentList</span></span>|<span data-ttu-id="625f5-123">对象的数组，这些对象指定作业所采用的参数。</span><span class="sxs-lookup"><span data-stu-id="625f5-123">An array of objects that specify arguments that the job takes.</span></span>|
|<span data-ttu-id="625f5-124">RunAs32</span><span class="sxs-lookup"><span data-stu-id="625f5-124">RunAs32</span></span>|<span data-ttu-id="625f5-125">一个布尔值，指定是否在32位进程中运行作业。</span><span class="sxs-lookup"><span data-stu-id="625f5-125">A boolean value that specifies whether to run the job in a 32-bit process.</span></span>|

<span data-ttu-id="625f5-126">下面的代码创建一个参数字典对象并设置 Name 和 ScriptBlock 参数。</span><span class="sxs-lookup"><span data-stu-id="625f5-126">The following code creates a parameter dictionary object and sets the Name and ScriptBlock parameters.</span></span>

```csharp
string schedJobDefName = "MySampleSchedJob";
Dictionary<string, object> jobDefParameters = new Dictionary<string, object>();
jobDefParameters.Add("Name", schedJobDefName);      // Unique name is required.

ScriptBlock scriptBlock = ScriptBlock.Create(@"1..5 | foreach {sleep 1; ""SchedJobOutput $_""}");
jobDefParameters.Add("ScriptBlock", scriptBlock);  // A scriptblock or script FilePath
                                                   // is required.
```

## <a name="creating-the-invocation-and-job-definition-objects"></a><span data-ttu-id="625f5-127">创建调用和作业定义对象</span><span class="sxs-lookup"><span data-stu-id="625f5-127">Creating the Invocation and Job Definition Objects</span></span>

<span data-ttu-id="625f5-128">然后，创建 ScheduledJobInvocationInfo 和 ScheduledJobDefinition 对象以运行作业。</span><span class="sxs-lookup"><span data-stu-id="625f5-128">You then create ScheduledJobInvocationInfo and ScheduledJobDefinition objects to run the job.</span></span> <span data-ttu-id="625f5-129">下面的代码对此进行了演示。</span><span class="sxs-lookup"><span data-stu-id="625f5-129">The following code demonstrates this.</span></span>

```csharp
ScheduledJobInvocationInfo jobInvocationInfo = new ScheduledJobInvocationInfo(
    nw JobDefinition(typeof(ScheduledJobSourceAdapter), scriptBlock.ToString(), schedJobDefName),
    jobDefParameters);

schedJobDefinition = new ScheduledJobDefinition(
    jobInvocationInfo,                          // Defines the PowerShell job to run.
    new ScheduledJobTrigger[1] { jobTrigger },  // Defines when to run the PowerShell job.
    null,                                       // No custom options.  We accept default.
    null);                                      // No credentials.  PowerShell job is run
                                                // in default Task Scheduler process, account.
```

## <a name="registering-the-job-with-the-task-scheduler"></a><span data-ttu-id="625f5-130">将作业注册到任务计划程序</span><span class="sxs-lookup"><span data-stu-id="625f5-130">Registering the Job with the Task Scheduler</span></span>

<span data-ttu-id="625f5-131">下面的代码向 Windows 任务计划程序注册作业。</span><span class="sxs-lookup"><span data-stu-id="625f5-131">The following code registers the job with the Windows Task Scheduler.</span></span>

```csharp
schedJobDefinition.Register();
registrationSucceeded = true;
Console.WriteLine("Scheduled job has been registered.  Waiting 30 seconds for it to be started and run.");
```

## <a name="complete-code-example"></a><span data-ttu-id="625f5-132">完整的代码示例</span><span class="sxs-lookup"><span data-stu-id="625f5-132">Complete Code Example</span></span>

<span data-ttu-id="625f5-133">下面是从中获取了前面的代码段的完整代码示例。</span><span class="sxs-lookup"><span data-stu-id="625f5-133">The following is the complete code example from which the previous snippets were taken.</span></span>

```csharp
using System;
using System.Threading;
using System.Collections.Generic;
using System.Management.Automation;             // Windows PowerShell namespace.
using Microsoft.PowerShell.ScheduledJob;        // Windows PowerShell ScheduledJob namespace.

namespace Microsoft.Samples.PowerShell.ScheduledJob
{
    /// <summary>
    /// This class contains the Main entry point for the application.
    /// </summary>
    public class ScheduledJobSample
    {
        /// <summary>
        /// This sample shows how to use the PowerShell ScheduledJob API to create
        /// a simple PowerShell scheduled job, register it with a trigger object
        /// that defines when the job will run and retrieve job run results from
        /// the job file store.
        /// </summary>
        /// <param name="args"></param>
        public static void Main(string[] args)
        {
            // ScheduledJobDefinition contains all elements of a PowerShell scheduled
            // job including the PowerShell job script or script file path, scheduling
            // triggers, and scheduling options.
            ScheduledJobDefinition schedJobDefinition = null;
            bool registrationSucceeded = false;

            try
            {
                // First create a scheduled job trigger object.  This object will
                // define when the PowerShell job is scheduled to run.  For this
                // example we will create a trigger to run the job just one time
                // 20 seconds after the trigger object is created.
                // Note: If you are stepping through this code in a debugger you
                // may want to increase the 20 seconds value so that the trigger time
                // remains in the future once you register the scheduled job.
                ScheduledJobTrigger jobTrigger = ScheduledJobTrigger.CreateOnceTrigger(
                    DateTime.Now.AddSeconds(20),        // Create trigger to start job 20 seconds after now.
                    TimeSpan.Zero,                      // No random delay
                    null,                               // No repetition interval time
                    null,                               // No repetition interval duration
                    1,                                  // Trigger Id
                    true);                              // Create trigger enabled

                // Create a parameter dictionary that defines the PowerShell job.
                // For this example we will create a simple script that runs for
                // 5 seconds generating output.
                // Here are the parameters supported to define the PowerShell job.
                // Name                 - Job name string.
                // ScriptBlock          - PowerShell ScriptBlock type.
                // FilePath             - PowerShell script file path string.
                // InitializationScript - PowerShell Scriptblock type.
                // ArgumentList         - object[] type.
                // RunAs32              - Switch (boolean type).
                string schedJobDefName = "MySampleSchedJob";
                Dictionary<string, object> jobDefParameters = new Dictionary<string, object>();
                jobDefParameters.Add("Name", schedJobDefName);      // Unique name is required.

                ScriptBlock scriptBlock = ScriptBlock.Create(@"1..5 | foreach {sleep 1; ""SchedJobOutput $_""}");
                jobDefParameters.Add("ScriptBlock", scriptBlock);  // A scriptblock or script FilePath
                                                                   // is required.

                // Now create a JobInvocation object that contains all information about
                // the PowerShell job to run.
                ScheduledJobInvocationInfo jobInvocationInfo = new ScheduledJobInvocationInfo(
                    new JobDefinition(typeof(ScheduledJobSourceAdapter), scriptBlock.ToString(), schedJobDefName),
                    jobDefParameters);

                // Finally create the scheduled job definition object that pulls all
                // of this information together.
                schedJobDefinition = new ScheduledJobDefinition(
                    jobInvocationInfo,                          // Defines the PowerShell job to run.
                    new ScheduledJobTrigger[1] { jobTrigger },  // Defines when to run the PowerShell job.
                    null,                                       // No custom options.  We accept default.
                    null);                                      // No credentials.  PowerShell job is run
                                                                // in default Task Scheduler process, account.

                // Next we register this scheduled job object with Windows Task Scheduler.
                // The Task Scheduler will run the PowerShell script based on the provided job trigger.
                schedJobDefinition.Register();
                registrationSucceeded = true;
                Console.WriteLine("Scheduled job has been registered.  Waiting 30 seconds for it to be started and run.");

                // You can see this PowerShell job task registered in the Task Scheduler UI.
                // Look under path: Task Scheduler Library\Microsoft\Windows\PowerShell\ScheduledJobs

                // Wait for Task Scheduler to run the PowerShell job.  This should happen in 20 seconds
                // and then the job will take about 5 seconds to run.  If PowerShell job task doesn't
                // run try increasing the trigger time in the ScheduledJobTrigger object.  You can also
                // run this task manually from the Task Scheduler UI.
                for (int count = 1; count < 31; ++count)
                {
                    Thread.Sleep(1000);
                    Console.WriteLine(count + " seconds elapsed");
                }

                Console.WriteLine();
                Console.WriteLine("Job run results.");
                Console.WriteLine();

                // Since the PowerShell job runs in a non-interactive Task Scheduler
                // process the job status and output data is written to a file based
                // job store and the directory location is the current user local app
                // data ($env:LOCALAPPDATA).
                // This job store can be accessed through the ScheduledJobSourceAdapter class.
                ScheduledJobSourceAdapter schedJobSourceAdapter = new ScheduledJobSourceAdapter();
                IList<Job2> jobRuns = schedJobSourceAdapter.GetJobs();
                foreach (var jobRun in jobRuns)
                {
                    // Check for jobs in finished state.
                    // Note that job data is not written to the job store until the job
                    // has reached a finished state.
                    JobState jobState = jobRun.JobStateInfo.State;
                    if (jobState == JobState.Completed ||
                        jobState == JobState.Stopped ||
                        jobState == JobState.Failed)
                    {
                        // Write job run finished state.
                        Console.WriteLine("Job Status: " + jobRun.JobStateInfo.State);
                        Console.WriteLine();
                        Console.WriteLine("Job Data");

                        // Write output data.
                        foreach (var item in jobRun.Output)
                        {
                            Console.WriteLine(item.ToString());
                        }

                        // Write any errors.
                        foreach (var item in jobRun.Error)
                        {
                            Console.WriteLine(item.ToString());
                        }
                    }
                }

                Console.WriteLine();
                Console.WriteLine("Press any key to continue...");
                Console.ReadKey();
            }
            catch (ScheduledJobException e)
            {
                Console.WriteLine("Error: " + e.Message);
            }
            finally
            {
                // Unregister this scheduled job or an error will be thrown when
                // running this sample code again (scheduled job already exists.)
                // because all registered scheduled jobs must have a unique name.
                if (registrationSucceeded)
                {
                    schedJobDefinition.Remove(true);
                }
            }
        }
    }
}
```

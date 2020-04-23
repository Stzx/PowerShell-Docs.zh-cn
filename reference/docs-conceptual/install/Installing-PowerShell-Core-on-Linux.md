---
title: 在 Linux 上安装 PowerShell
description: 介绍如何在各种 Linux 分发版上安装 PowerShell
ms.date: 03/09/2020
ms.openlocfilehash: 31da32b81dbbcf4b46fd5f0cd9d921f28f434763
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/22/2020
ms.locfileid: "80500554"
---
# <a name="installing-powershell-on-linux"></a><span data-ttu-id="03731-103">在 Linux 上安装 PowerShell</span><span class="sxs-lookup"><span data-stu-id="03731-103">Installing PowerShell on Linux</span></span>

<span data-ttu-id="03731-104">支持 [Ubuntu 16.04][u16]、[Ubuntu 18.04][u1804]、[Ubuntu 18.10][u1810]、[Ubuntu 19.04][u1904]、[Debian 8][deb8]、[Debian 9][deb9]、[Debian 10][deb10]、[Alpine 3.9 和 3.10][alpine]、[CentOS 7][cos]、[Red Hat Enterprise Linux (RHEL) 7][rhel7]、[openSUSE 42.3][opensuse]、[openSUSE Leap 15][opensuse]、[Fedora 28][fedora]、[Fedora 29][fedora]、[Fedora 30][fedora] 和 [Arch Linux][arch]。</span><span class="sxs-lookup"><span data-stu-id="03731-104">Supports [Ubuntu 16.04][u16], [Ubuntu 18.04][u1804], [Ubuntu 18.10][u1810], [Ubuntu 19.04][u1904], [Debian 8][deb8], [Debian 9][deb9], [Debian 10][deb10], [Alpine 3.9 and 3.10][alpine], [CentOS 7][cos], [Red Hat Enterprise Linux (RHEL) 7][rhel7], [openSUSE 42.3][opensuse], [openSUSE Leap 15][opensuse], [Fedora 28][fedora], [Fedora 29][fedora], [Fedora 30][fedora], and [Arch Linux][arch].</span></span>

<span data-ttu-id="03731-105">对于未获得官方支持的 Linux 分发，可尝试使用 [PowerShell Snap 包][snap]安装 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="03731-105">For Linux distributions that aren't officially supported, you can try to install PowerShell using the [PowerShell Snap Package][snap].</span></span> <span data-ttu-id="03731-106">还可尝试直接使用 Linux [`tar.gz`存档][tar] 部署 PowerShell 二进制文件，但是需要在各个步骤中基于 OS 设置必要的依赖项。</span><span class="sxs-lookup"><span data-stu-id="03731-106">You can also try deploying PowerShell binaries directly using the Linux [`tar.gz` archive][tar], but you would need to set up the necessary dependencies based on the OS in separate steps.</span></span>

<span data-ttu-id="03731-107">GitHub [页中将 Debian 包 ][]页面上提供有所有可用包。</span><span class="sxs-lookup"><span data-stu-id="03731-107">All packages are available on our GitHub [releases][] page.</span></span> <span data-ttu-id="03731-108">安装包以后，从终端运行 `pwsh`。</span><span class="sxs-lookup"><span data-stu-id="03731-108">After the package is installed, run `pwsh` from a terminal.</span></span> <span data-ttu-id="03731-109">若已安装 `pwsh-preview`预览版[，请运行 ](#installing-preview-releases)。</span><span class="sxs-lookup"><span data-stu-id="03731-109">Run `pwsh-preview` if you installed a [Preview release](#installing-preview-releases).</span></span>

> [!NOTE]
> <span data-ttu-id="03731-110">PowerShell 7 是就地升级，升级后会删除 PowerShell Core 6.x。</span><span class="sxs-lookup"><span data-stu-id="03731-110">PowerShell 7 is an in-place upgrade that removes PowerShell Core 6.x.</span></span>
>
> <span data-ttu-id="03731-111">`/usr/local/microsoft/powershell/6` 文件夹被替换为 `/usr/local/microsoft/powershell/7`。</span><span class="sxs-lookup"><span data-stu-id="03731-111">The `/usr/local/microsoft/powershell/6` folder is replaced by `/usr/local/microsoft/powershell/7`.</span></span>
>
> <span data-ttu-id="03731-112">如果需要与 PowerShell 7 并行运行 PowerShell 6，请使用[二进制存档](#binary-archives)方法重新安装 PowerShell 6。</span><span class="sxs-lookup"><span data-stu-id="03731-112">If you need to run PowerShell 6 side-by-side with PowerShell 7, reinstall PowerShell 6 using the [binary archive](#binary-archives) method.</span></span>

[u16]: #ubuntu-1604
[u1804]: #ubuntu-1804
[u1810]: #ubuntu-1810
[u1904]: #ubuntu-1904
[deb8]: #debian-8
[deb9]: #debian-9
[deb10]: #debian-10
[alpine]: #alpine-39-and-310
[cos]: #centos-7
[rhel7]: #red-hat-enterprise-linux-rhel-7
[opensuse]: #opensuse
[fedora]: #fedora
[arch]: #arch-linux
[snap]: #snap-package
[tar]: #binary-archives


## <a name="installing-preview-releases"></a><span data-ttu-id="03731-113">安装预览版本</span><span class="sxs-lookup"><span data-stu-id="03731-113">Installing Preview Releases</span></span>

<span data-ttu-id="03731-114">通过包存储库安装适用于 Linux 的 PowerShell 预览版本时，包名称从 `powershell` 更改为 `powershell-preview`。</span><span class="sxs-lookup"><span data-stu-id="03731-114">When installing a PowerShell Preview release for Linux via a Package Repository, the package name changes from `powershell` to `powershell-preview`.</span></span>

<span data-ttu-id="03731-115">直接下载安装不会更改包名称（文件名除外）。</span><span class="sxs-lookup"><span data-stu-id="03731-115">Installing via direct download doesn't change, other than the file name.</span></span>

<span data-ttu-id="03731-116">下表包含使用各种包管理器安装稳定包和预览包的命令：</span><span class="sxs-lookup"><span data-stu-id="03731-116">The following table contains the commands to install the stable and preview packages using the various package managers:</span></span>

| <span data-ttu-id="03731-117">分配</span><span class="sxs-lookup"><span data-stu-id="03731-117">Distribution(s)</span></span> |            <span data-ttu-id="03731-118">稳定包命令</span><span class="sxs-lookup"><span data-stu-id="03731-118">Stable Command</span></span>            |               <span data-ttu-id="03731-119">预览包命令</span><span class="sxs-lookup"><span data-stu-id="03731-119">Preview Command</span></span>                |
| --------------- | ------------------------------------ | -------------------------------------------- |
| <span data-ttu-id="03731-120">Ubuntu、Debian</span><span class="sxs-lookup"><span data-stu-id="03731-120">Ubuntu, Debian</span></span>  | `sudo apt-get install -y powershell` | `sudo apt-get install -y powershell-preview` |
| <span data-ttu-id="03731-121">CentOS、RedHat</span><span class="sxs-lookup"><span data-stu-id="03731-121">CentOS, RedHat</span></span>  | `sudo yum install -y powershell`     | `sudo yum install -y powershell-preview`     |
| <span data-ttu-id="03731-122">Fedora</span><span class="sxs-lookup"><span data-stu-id="03731-122">Fedora</span></span>          | `sudo dnf install -y powershell`     | `sudo dnf install -y powershell-preview`     |

## <a name="ubuntu-1604"></a><span data-ttu-id="03731-123">Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="03731-123">Ubuntu 16.04</span></span>

### <a name="installation-via-package-repository---ubuntu-1604"></a><span data-ttu-id="03731-124">通过包存储库安装 - Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="03731-124">Installation via Package Repository - Ubuntu 16.04</span></span>

<span data-ttu-id="03731-125">为简化安装和更新，已将适用于 Linux 的 PowerShell 发布到包存储库。</span><span class="sxs-lookup"><span data-stu-id="03731-125">PowerShell for Linux is published to package repositories for easy installation and updates.</span></span>

<span data-ttu-id="03731-126">首选方法如下所示：</span><span class="sxs-lookup"><span data-stu-id="03731-126">The preferred method is as follows:</span></span>

```sh
# Download the Microsoft repository GPG keys
wget -q https://packages.microsoft.com/config/ubuntu/16.04/packages-microsoft-prod.deb

# Register the Microsoft repository GPG keys
sudo dpkg -i packages-microsoft-prod.deb

# Update the list of products
sudo apt-get update

# Install PowerShell
sudo apt-get install -y powershell

# Start PowerShell
pwsh
```

<span data-ttu-id="03731-127">以超级用户身份注册 Microsoft 存储库一次。</span><span class="sxs-lookup"><span data-stu-id="03731-127">As superuser, register the Microsoft repository once.</span></span> <span data-ttu-id="03731-128">注册后，可以通过 `sudo apt-get upgrade powershell` 更新 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="03731-128">After registration, you can update PowerShell with `sudo apt-get upgrade powershell`.</span></span>

### <a name="installation-via-direct-download---ubuntu-1604"></a><span data-ttu-id="03731-129">通过直接下载进行安装 - Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="03731-129">Installation via Direct Download - Ubuntu 16.04</span></span>

<span data-ttu-id="03731-130">从`powershell-lts_7.0.0-1.ubuntu.16.04_amd64.deb`版本[页中将 Debian 包 ][] 下载到 Ubuntu 计算机。</span><span class="sxs-lookup"><span data-stu-id="03731-130">Download the Debian package `powershell-lts_7.0.0-1.ubuntu.16.04_amd64.deb` from the [releases][] page onto the Ubuntu machine.</span></span>

<span data-ttu-id="03731-131">然后在终端中执行以下命令：</span><span class="sxs-lookup"><span data-stu-id="03731-131">Then, in the terminal, execute the following commands:</span></span>

```sh
sudo dpkg -i powershell-lts_7.0.0-1.ubuntu.16.04_amd64.deb
sudo apt-get install -f
```

> [!NOTE]
> <span data-ttu-id="03731-132">`dpkg -i` 命令失败，未满足依赖项。</span><span class="sxs-lookup"><span data-stu-id="03731-132">The `dpkg -i` command fails with unmet dependencies.</span></span> <span data-ttu-id="03731-133">下一命令 `apt-get install -f` 解决此类问题，然后完成 PowerShell 包配置。</span><span class="sxs-lookup"><span data-stu-id="03731-133">The next command, `apt-get install -f` resolves these issues then finishes configuring the PowerShell package.</span></span>

### <a name="uninstallation---ubuntu-1604"></a><span data-ttu-id="03731-134">卸载 - Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="03731-134">Uninstallation - Ubuntu 16.04</span></span>

```sh
sudo apt-get remove powershell
```

## <a name="ubuntu-1804"></a><span data-ttu-id="03731-135">Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="03731-135">Ubuntu 18.04</span></span>

### <a name="installation-via-package-repository---ubuntu-1804"></a><span data-ttu-id="03731-136">通过包存储库安装 - Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="03731-136">Installation via Package Repository - Ubuntu 18.04</span></span>

<span data-ttu-id="03731-137">为简化安装和更新，已将适用于 Linux 的 PowerShell 发布到包存储库。</span><span class="sxs-lookup"><span data-stu-id="03731-137">PowerShell for Linux is published to package repositories for easy installation and updates.</span></span>

<span data-ttu-id="03731-138">首选方法如下所示：</span><span class="sxs-lookup"><span data-stu-id="03731-138">The preferred method is as follows:</span></span>

```sh
# Download the Microsoft repository GPG keys
wget -q https://packages.microsoft.com/config/ubuntu/18.04/packages-microsoft-prod.deb

# Register the Microsoft repository GPG keys
sudo dpkg -i packages-microsoft-prod.deb

# Update the list of products
sudo apt-get update

# Enable the "universe" repositories
sudo add-apt-repository universe

# Install PowerShell
sudo apt-get install -y powershell

# Start PowerShell
pwsh
```

<span data-ttu-id="03731-139">以超级用户身份注册 Microsoft 存储库一次。</span><span class="sxs-lookup"><span data-stu-id="03731-139">As superuser, register the Microsoft repository once.</span></span> <span data-ttu-id="03731-140">注册后，可以通过 `sudo apt-get upgrade powershell` 更新 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="03731-140">After registration, you can update PowerShell with `sudo apt-get upgrade powershell`.</span></span>

### <a name="installation-via-direct-download---ubuntu-1804"></a><span data-ttu-id="03731-141">通过直接下载安装 - Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="03731-141">Installation via Direct Download - Ubuntu 18.04</span></span>

<span data-ttu-id="03731-142">从`powershell-lts_7.0.0-1.ubuntu.18.04_amd64.deb`版本[页中将 Debian 包 ][] 下载到 Ubuntu 计算机。</span><span class="sxs-lookup"><span data-stu-id="03731-142">Download the Debian package `powershell-lts_7.0.0-1.ubuntu.18.04_amd64.deb` from the [releases][] page onto the Ubuntu machine.</span></span>

<span data-ttu-id="03731-143">然后在终端中执行以下命令：</span><span class="sxs-lookup"><span data-stu-id="03731-143">Then, in the terminal, execute the following commands:</span></span>

```sh
sudo dpkg -i powershell-lts_7.0.0-1.ubuntu.18.04_amd64.deb
sudo apt-get install -f
```

> [!NOTE]
> <span data-ttu-id="03731-144">`dpkg -i` 命令失败，未满足依赖项。</span><span class="sxs-lookup"><span data-stu-id="03731-144">The `dpkg -i` command fails with unmet dependencies.</span></span> <span data-ttu-id="03731-145">下一命令 `apt-get install -f` 解决此类问题，然后完成 PowerShell 包配置。</span><span class="sxs-lookup"><span data-stu-id="03731-145">The next command, `apt-get install -f` resolves these issues then finishes configuring the PowerShell package.</span></span>

### <a name="uninstallation---ubuntu-1804"></a><span data-ttu-id="03731-146">卸载 - Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="03731-146">Uninstallation - Ubuntu 18.04</span></span>

```sh
sudo apt-get remove powershell
```

## <a name="ubuntu-1810"></a><span data-ttu-id="03731-147">Ubuntu 18.10</span><span class="sxs-lookup"><span data-stu-id="03731-147">Ubuntu 18.10</span></span>

<span data-ttu-id="03731-148">安装是通过 `snapd` 受到支持。</span><span class="sxs-lookup"><span data-stu-id="03731-148">Installation is supported via `snapd`.</span></span> <span data-ttu-id="03731-149">有关说明，请参阅 [Snap 包][snap]。</span><span class="sxs-lookup"><span data-stu-id="03731-149">For instructions, see [Snap Package][snap].</span></span>

> [!NOTE]
> <span data-ttu-id="03731-150">Ubuntu 18.10 是[支持社区](https://www.ubuntu.com/about/release-cycle)的[过渡版本](../powershell-support-lifecycle.md)。</span><span class="sxs-lookup"><span data-stu-id="03731-150">Ubuntu 18.10 is an [interim release](https://www.ubuntu.com/about/release-cycle) that's [community supported](../powershell-support-lifecycle.md).</span></span>

## <a name="ubuntu-1904"></a><span data-ttu-id="03731-151">Ubuntu 19.04</span><span class="sxs-lookup"><span data-stu-id="03731-151">Ubuntu 19.04</span></span>

<span data-ttu-id="03731-152">安装是通过 `snapd` 受到支持。</span><span class="sxs-lookup"><span data-stu-id="03731-152">Installation is supported via `snapd`.</span></span> <span data-ttu-id="03731-153">有关说明，请参阅 [Snap 包][snap]。</span><span class="sxs-lookup"><span data-stu-id="03731-153">For instructions, see [Snap Package][snap].</span></span>

> [!NOTE]
> <span data-ttu-id="03731-154">Ubuntu 19.04 是[社区支持](https://www.ubuntu.com/about/release-cycle)的[过渡版本](../powershell-support-lifecycle.md)。</span><span class="sxs-lookup"><span data-stu-id="03731-154">Ubuntu 19.04 is an [interim release](https://www.ubuntu.com/about/release-cycle) that's [community supported](../powershell-support-lifecycle.md).</span></span>

## <a name="debian-8"></a><span data-ttu-id="03731-155">Debian 8</span><span class="sxs-lookup"><span data-stu-id="03731-155">Debian 8</span></span>

### <a name="installation-via-package-repository---debian-8"></a><span data-ttu-id="03731-156">通过包存储库安装 - Debian 8</span><span class="sxs-lookup"><span data-stu-id="03731-156">Installation via Package Repository - Debian 8</span></span>

<span data-ttu-id="03731-157">为简化安装和更新，已将适用于 Linux 的 PowerShell 发布到包存储库。</span><span class="sxs-lookup"><span data-stu-id="03731-157">PowerShell for Linux is published to package repositories for easy installation and updates.</span></span>

<span data-ttu-id="03731-158">首选方法如下所示：</span><span class="sxs-lookup"><span data-stu-id="03731-158">The preferred method is as follows:</span></span>

```sh
# Install system components
sudo apt-get update
sudo apt-get install -y curl apt-transport-https

# Import the public repository GPG keys
curl https://packages.microsoft.com/keys/microsoft.asc | sudo apt-key add -

# Register the Microsoft Product feed
sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/microsoft-debian-jessie-prod jessie main" > /etc/apt/sources.list.d/microsoft.list'

# Update the list of products
sudo apt-get update

# Install PowerShell
sudo apt-get install -y powershell

# Start PowerShell
pwsh
```

<span data-ttu-id="03731-159">以超级用户身份注册 Microsoft 存储库一次。</span><span class="sxs-lookup"><span data-stu-id="03731-159">As superuser, register the Microsoft repository once.</span></span> <span data-ttu-id="03731-160">注册后，可以通过 `sudo apt-get upgrade powershell` 更新 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="03731-160">After registration, you can update PowerShell with `sudo apt-get upgrade powershell`.</span></span>

## <a name="debian-9"></a><span data-ttu-id="03731-161">Debian 9</span><span class="sxs-lookup"><span data-stu-id="03731-161">Debian 9</span></span>

### <a name="installation-via-package-repository---debian-9"></a><span data-ttu-id="03731-162">通过包存储库安装 - Debian 9</span><span class="sxs-lookup"><span data-stu-id="03731-162">Installation via Package Repository - Debian 9</span></span>

<span data-ttu-id="03731-163">为简化安装和更新，已将适用于 Linux 的 PowerShell 发布到包存储库。</span><span class="sxs-lookup"><span data-stu-id="03731-163">PowerShell for Linux is published to package repositories for easy installation and updates.</span></span>

<span data-ttu-id="03731-164">首选方法如下所示：</span><span class="sxs-lookup"><span data-stu-id="03731-164">The preferred method is as follows:</span></span>

```sh
# Install system components
sudo apt-get update
sudo apt-get install -y curl gnupg apt-transport-https

# Import the public repository GPG keys
curl https://packages.microsoft.com/keys/microsoft.asc | sudo apt-key add -

# Register the Microsoft Product feed
sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/microsoft-debian-stretch-prod stretch main" > /etc/apt/sources.list.d/microsoft.list'

# Update the list of products
sudo apt-get update

# Install PowerShell
sudo apt-get install -y powershell

# Start PowerShell
pwsh
```

<span data-ttu-id="03731-165">以超级用户身份注册 Microsoft 存储库一次。</span><span class="sxs-lookup"><span data-stu-id="03731-165">As superuser, register the Microsoft repository once.</span></span> <span data-ttu-id="03731-166">注册后，可以通过 `sudo apt-get upgrade powershell` 更新 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="03731-166">After registration, you can update PowerShell with `sudo apt-get upgrade powershell`.</span></span>

### <a name="installation-via-direct-download---debian-9"></a><span data-ttu-id="03731-167">通过直接下载进行安装 - Debian 9</span><span class="sxs-lookup"><span data-stu-id="03731-167">Installation via Direct Download - Debian 9</span></span>

<span data-ttu-id="03731-168">从`powershell-lts_7.0.0-1.debian.9_amd64.deb`版本[页中将 Debian 包 ][] 下载到 Debian 计算机。</span><span class="sxs-lookup"><span data-stu-id="03731-168">Download the Debian package `powershell-lts_7.0.0-1.debian.9_amd64.deb` from the [releases][] page onto the Debian machine.</span></span>

<span data-ttu-id="03731-169">然后在终端中执行以下命令：</span><span class="sxs-lookup"><span data-stu-id="03731-169">Then, in the terminal, execute the following commands:</span></span>

```sh
sudo dpkg -i powershell-lts_7.0.0-1.debian.9_amd64.deb
sudo apt-get install -f
```

### <a name="uninstallation---debian-9"></a><span data-ttu-id="03731-170">卸载 - Debian 9</span><span class="sxs-lookup"><span data-stu-id="03731-170">Uninstallation - Debian 9</span></span>

```sh
sudo apt-get remove powershell
```

## <a name="debian-10"></a><span data-ttu-id="03731-171">Debian 10</span><span class="sxs-lookup"><span data-stu-id="03731-171">Debian 10</span></span>

> [!NOTE]
> <span data-ttu-id="03731-172">Debian 10 仅在 PowerShell 7.0 以及更新版本中受到支持。</span><span class="sxs-lookup"><span data-stu-id="03731-172">Debian 10 is only supported in PowerShell 7.0 and newer.</span></span>

### <a name="installation-via-package-repository---debian-10"></a><span data-ttu-id="03731-173">通过包存储库安装 - Debian 10</span><span class="sxs-lookup"><span data-stu-id="03731-173">Installation via Package Repository - Debian 10</span></span>

<span data-ttu-id="03731-174">为简化安装和更新，已将适用于 Linux 的 PowerShell 发布到包存储库。</span><span class="sxs-lookup"><span data-stu-id="03731-174">PowerShell for Linux is published to package repositories for easy installation and updates.</span></span>

<span data-ttu-id="03731-175">首选方法如下所示：</span><span class="sxs-lookup"><span data-stu-id="03731-175">The preferred method is as follows:</span></span>

```sh
# Download the Microsoft repository GPG keys
wget https://packages.microsoft.com/config/debian/10/packages-microsoft-prod.deb

# Register the Microsoft repository GPG keys
sudo dpkg -i packages-microsoft-prod.deb

# Update the list of products
sudo apt-get update

# Install PowerShell
sudo apt-get install -y powershell

# Start PowerShell
pwsh
```

### <a name="installation-via-direct-download---debian-10"></a><span data-ttu-id="03731-176">通过直接下载进行安装 - Debian 10</span><span class="sxs-lookup"><span data-stu-id="03731-176">Installation via Direct Download - Debian 10</span></span>

<span data-ttu-id="03731-177">从`powershell_7.0.0-linux-x64.tar.gz`版本[页中将 Debian 包 ][] 下载到 Debian 计算机。</span><span class="sxs-lookup"><span data-stu-id="03731-177">Download the tar.gz package `powershell_7.0.0-linux-x64.tar.gz` from the [releases][] page onto the Debian machine.</span></span>

<span data-ttu-id="03731-178">然后在终端中执行以下命令：</span><span class="sxs-lookup"><span data-stu-id="03731-178">Then, in the terminal, execute the following commands:</span></span>

```sh
sudo apt-get update
# install the requirements
sudo apt-get install -y \
        less \
        locales \
        ca-certificates \
        libicu63 \
        libssl1.1 \
        libc6 \
        libgcc1 \
        libgssapi-krb5-2 \
        liblttng-ust0 \
        libstdc++6 \
        zlib1g \
        curl

# Download the powershell '.tar.gz' archive
curl -L  https://github.com/PowerShell/PowerShell/releases/download/v7.0.0/powershell-7.0.0-linux-x64.tar.gz -o /tmp/powershell.tar.gz

# Create the target folder where powershell will be placed
sudo mkdir -p /opt/microsoft/powershell/7

# Expand powershell to the target folder
sudo tar zxf /tmp/powershell.tar.gz -C /opt/microsoft/powershell/7

# Set execute permissions
sudo chmod +x /opt/microsoft/powershell/7/pwsh

# Create the symbolic link that points to pwsh
sudo ln -s /opt/microsoft/powershell/7/pwsh /usr/bin/pwsh

# Start PowerShell
pwsh
```

## <a name="alpine-39-and-310"></a><span data-ttu-id="03731-179">Alpine 3.9 和 Alpine 3.10</span><span class="sxs-lookup"><span data-stu-id="03731-179">Alpine 3.9 and 3.10</span></span>

> [!NOTE]
> <span data-ttu-id="03731-180">Alpine 3.9 和 Alpine 3.10 仅在 PowerShell 7.0 以及更新版本中受到支持。</span><span class="sxs-lookup"><span data-stu-id="03731-180">Alpine 3.9 and 3.10 are only supported in PowerShell 7.0 and newer.</span></span>

### <a name="installation-via-direct-download---alpine-39-and-310"></a><span data-ttu-id="03731-181">通过直接下载进行安装 - Alpine 3.9 和 3.10</span><span class="sxs-lookup"><span data-stu-id="03731-181">Installation via Direct Download - Alpine 3.9 and 3.10</span></span>

<span data-ttu-id="03731-182">从`powershell-7.0.0-linux-alpine-x64.tar.gz`版本[页中将 Debian 包 ][] 下载到 Alpine 计算机。</span><span class="sxs-lookup"><span data-stu-id="03731-182">Download the tar.gz package `powershell-7.0.0-linux-alpine-x64.tar.gz` from the [releases][] page onto the Alpine machine.</span></span>

<span data-ttu-id="03731-183">然后在终端中执行以下命令：</span><span class="sxs-lookup"><span data-stu-id="03731-183">Then, in the terminal, execute the following commands:</span></span>

```sh
# install the requirements
sudo apk add --no-cache \
    ca-certificates \
    less \
    ncurses-terminfo-base \
    krb5-libs \
    libgcc \
    libintl \
    libssl1.1 \
    libstdc++ \
    tzdata \
    userspace-rcu \
    zlib \
    icu-libs \
    curl

sudo apk -X https://dl-cdn.alpinelinux.org/alpine/edge/main add --no-cache \
    lttng-ust

# Download the powershell '.tar.gz' archive
curl -L https://github.com/PowerShell/PowerShell/releases/download/v7.0.0/powershell-7.0.0-linux-alpine-x64.tar.gz -o /tmp/powershell.tar.gz

# Create the target folder where powershell will be placed
sudo mkdir -p /opt/microsoft/powershell/7

# Expand powershell to the target folder
sudo tar zxf /tmp/powershell.tar.gz -C /opt/microsoft/powershell/7

# Set execute permissions
sudo chmod +x /opt/microsoft/powershell/7/pwsh

# Create the symbolic link that points to pwsh
sudo ln -s /opt/microsoft/powershell/7/pwsh /usr/bin/pwsh

# Start PowerShell
pwsh
```

## <a name="centos-7"></a><span data-ttu-id="03731-184">CentOS 7</span><span class="sxs-lookup"><span data-stu-id="03731-184">CentOS 7</span></span>

> [!NOTE]
> <span data-ttu-id="03731-185">此包可以在 Oracle Linux 7 上运行。</span><span class="sxs-lookup"><span data-stu-id="03731-185">This package works on Oracle Linux 7.</span></span>

### <a name="installation-via-package-repository-preferred---centos-7"></a><span data-ttu-id="03731-186">通过包存储库安装（首选）- CentOS 7</span><span class="sxs-lookup"><span data-stu-id="03731-186">Installation via Package Repository (preferred) - CentOS 7</span></span>

<span data-ttu-id="03731-187">为简化安装和更新，已将适用于 Linux 的 PowerShell 发布到正式的 Microsoft 存储库。</span><span class="sxs-lookup"><span data-stu-id="03731-187">PowerShell for Linux is published to official Microsoft repositories for easy installation and updates.</span></span>

```sh
# Register the Microsoft RedHat repository
curl https://packages.microsoft.com/config/rhel/7/prod.repo | sudo tee /etc/yum.repos.d/microsoft.repo

# Install PowerShell
sudo yum install -y powershell

# Start PowerShell
pwsh
```

<span data-ttu-id="03731-188">以超级用户身份注册 Microsoft 存储库一次。</span><span class="sxs-lookup"><span data-stu-id="03731-188">As superuser, register the Microsoft repository once.</span></span> <span data-ttu-id="03731-189">注册后，可以通过 `sudo yum update powershell` 更新 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="03731-189">After registration, you can update PowerShell with `sudo yum update powershell`.</span></span>

### <a name="installation-via-direct-download---centos-7"></a><span data-ttu-id="03731-190">通过直接下载进行安装 - CentOS 7</span><span class="sxs-lookup"><span data-stu-id="03731-190">Installation via Direct Download - CentOS 7</span></span>

<span data-ttu-id="03731-191">使用 [CentOS 7][]时，请从`powershell-lts-7.0.0-1.rhel.7.x86_64.rpm`版本[页中将 Debian 包 ][] 下载到 CentOS 计算机。</span><span class="sxs-lookup"><span data-stu-id="03731-191">Using [CentOS 7][], download the RPM package `powershell-lts-7.0.0-1.rhel.7.x86_64.rpm` from the [releases][] page onto the CentOS machine.</span></span>

<span data-ttu-id="03731-192">然后在终端中执行以下命令：</span><span class="sxs-lookup"><span data-stu-id="03731-192">Then, in the terminal, execute the following commands:</span></span>

```sh
sudo yum install powershell-lts-7.0.0-1.rhel.7.x86_64.rpm
```

<span data-ttu-id="03731-193">无需该中间下载步骤即可安装 RPM：</span><span class="sxs-lookup"><span data-stu-id="03731-193">You can install the RPM without the intermediate step of downloading it:</span></span>

```sh
sudo yum install https://github.com/PowerShell/PowerShell/releases/download/v7.0.0/powershell-lts-7.0.0-1.rhel.7.x86_64.rpm
```

### <a name="uninstallation---centos-7"></a><span data-ttu-id="03731-194">卸载 - CentOS 7</span><span class="sxs-lookup"><span data-stu-id="03731-194">Uninstallation - CentOS 7</span></span>

```sh
sudo yum remove powershell
```

[CentOS 7]: https://www.centos.org/download/

## <a name="red-hat-enterprise-linux-rhel-7"></a><span data-ttu-id="03731-196">Red Hat Enterprise Linux (RHEL) 7</span><span class="sxs-lookup"><span data-stu-id="03731-196">Red Hat Enterprise Linux (RHEL) 7</span></span>

### <a name="installation-via-package-repository-preferred---red-hat-enterprise-linux-rhel-7"></a><span data-ttu-id="03731-197">通过包存储库安装（首选）- Red Hat Enterprise Linux (RHEL) 7</span><span class="sxs-lookup"><span data-stu-id="03731-197">Installation via Package Repository (preferred) - Red Hat Enterprise Linux (RHEL) 7</span></span>

<span data-ttu-id="03731-198">为简化安装和更新，已将适用于 Linux 的 PowerShell 发布到正式的 Microsoft 存储库。</span><span class="sxs-lookup"><span data-stu-id="03731-198">PowerShell for Linux is published to official Microsoft repositories for easy installation and updates.</span></span>

```sh
# Register the Microsoft RedHat repository
curl https://packages.microsoft.com/config/rhel/7/prod.repo | sudo tee /etc/yum.repos.d/microsoft.repo

# Install PowerShell
sudo yum install -y powershell

# Start PowerShell
pwsh
```

<span data-ttu-id="03731-199">以超级用户身份注册 Microsoft 存储库一次。</span><span class="sxs-lookup"><span data-stu-id="03731-199">As superuser, register the Microsoft repository once.</span></span> <span data-ttu-id="03731-200">注册后，可以通过 `sudo yum update powershell` 更新 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="03731-200">After registration, you can update PowerShell with `sudo yum update powershell`.</span></span>

### <a name="installation-via-direct-download---red-hat-enterprise-linux-rhel-7"></a><span data-ttu-id="03731-201">通过直接下载进行安装 - Red Hat Enterprise Linux (RHEL) 7</span><span class="sxs-lookup"><span data-stu-id="03731-201">Installation via Direct Download - Red Hat Enterprise Linux (RHEL) 7</span></span>

<span data-ttu-id="03731-202">从`powershell-lts-7.0.0-1.rhel.7.x86_64.rpm`版本[页中将 Debian 包 ][] 下载到 Red Hat Enterprise Linux 计算机。</span><span class="sxs-lookup"><span data-stu-id="03731-202">Download the RPM package `powershell-lts-7.0.0-1.rhel.7.x86_64.rpm` from the [releases][] page onto the Red Hat Enterprise Linux machine.</span></span>

<span data-ttu-id="03731-203">然后在终端中执行以下命令：</span><span class="sxs-lookup"><span data-stu-id="03731-203">Then, in the terminal, execute the following commands:</span></span>

```sh
sudo yum install powershell-lts-7.0.0-1.rhel.7.x86_64.rpm
```

<span data-ttu-id="03731-204">无需该中间下载步骤即可安装 RPM：</span><span class="sxs-lookup"><span data-stu-id="03731-204">You can install the RPM without the intermediate step of downloading it:</span></span>

```sh
sudo yum install https://github.com/PowerShell/PowerShell/releases/download/v7.0.0/powershell-lts-7.0.0-1.rhel.7.x86_64.rpm
```

### <a name="uninstallation---red-hat-enterprise-linux-rhel-7"></a><span data-ttu-id="03731-205">卸载 - Red Hat Enterprise Linux (RHEL) 7</span><span class="sxs-lookup"><span data-stu-id="03731-205">Uninstallation - Red Hat Enterprise Linux (RHEL) 7</span></span>

```sh
sudo yum remove powershell
```

## <a name="opensuse"></a><span data-ttu-id="03731-206">OpenSUSE</span><span class="sxs-lookup"><span data-stu-id="03731-206">openSUSE</span></span>

### <a name="installation---opensuse-423"></a><span data-ttu-id="03731-207">安装 - openSUSE 42.3</span><span class="sxs-lookup"><span data-stu-id="03731-207">Installation - openSUSE 42.3</span></span>

```sh
# Install dependencies
zypper update && zypper --non-interactive install curl tar libicu52_1

# Download the powershell '.tar.gz' archive
curl -L https://github.com/PowerShell/PowerShell/releases/download/v7.0.0/powershell-7.0.0-linux-x64.tar.gz -o /tmp/powershell.tar.gz

# Create the target folder where powershell will be placed
mkdir -p /opt/microsoft/powershell/7

# Expand powershell to the target folder
tar zxf /tmp/powershell.tar.gz -C /opt/microsoft/powershell/7

# Set execute permissions
chmod +x /opt/microsoft/powershell/7/pwsh

# Create the symbolic link that points to pwsh
ln -s /opt/microsoft/powershell/7/pwsh /usr/bin/pwsh

# Start PowerShell
pwsh
```

### <a name="installation---opensuse-leap-15"></a><span data-ttu-id="03731-208">安装 - openSUSE Leap 15</span><span class="sxs-lookup"><span data-stu-id="03731-208">Installation - openSUSE Leap 15</span></span>

```sh
# Install dependencies
zypper update && zypper --non-interactive install curl tar gzip libopenssl1_0_0 libicu60_2

# Download the powershell '.tar.gz' archive
curl -L https://github.com/PowerShell/PowerShell/releases/download/v7.0.0/powershell-7.0.0-linux-x64.tar.gz -o /tmp/powershell.tar.gz

# Create the target folder where powershell will be placed
mkdir -p /opt/microsoft/powershell/7

# Expand powershell to the target folder
tar zxf /tmp/powershell.tar.gz -C /opt/microsoft/powershell/7

# Set execute permissions
chmod +x /opt/microsoft/powershell/7/pwsh

# Create the symbolic link that points to pwsh
ln -s /opt/microsoft/powershell/7/pwsh /usr/bin/pwsh

# Start PowerShell
pwsh
```

### <a name="uninstallation---opensuse-423-opensuse-leap-15"></a><span data-ttu-id="03731-209">卸载 - OpenSUSE 42.3、openSUSE Leap 15</span><span class="sxs-lookup"><span data-stu-id="03731-209">Uninstallation - openSUSE 42.3, openSUSE Leap 15</span></span>

```sh
rm -rf /usr/bin/pwsh /opt/microsoft/powershell
```

## <a name="fedora"></a><span data-ttu-id="03731-210">Fedora</span><span class="sxs-lookup"><span data-stu-id="03731-210">Fedora</span></span>

> [!NOTE]
> <span data-ttu-id="03731-211">Fedora 28 仅在 PowerShell 6.1 以及更新版本中受到支持。</span><span class="sxs-lookup"><span data-stu-id="03731-211">Fedora 28 is only supported in PowerShell 6.1 and newer.</span></span>

> [!NOTE]
> <span data-ttu-id="03731-212">Fedora 29 和 Fedora 30 仅在 PowerShell 7.0 以及更新版本中受到支持。</span><span class="sxs-lookup"><span data-stu-id="03731-212">Fedora 29 and 30 are only supported in PowerShell 7.0 and newer.</span></span>

### <a name="installation-via-package-repository-preferred---fedora-28-29-and-30"></a><span data-ttu-id="03731-213">通过包存储库安装（首选）- Fedora 28、Fedora 29 和 Fedora 30</span><span class="sxs-lookup"><span data-stu-id="03731-213">Installation via Package Repository (preferred) - Fedora 28, 29, and 30</span></span>

<span data-ttu-id="03731-214">为简化安装和更新，已将适用于 Linux 的 PowerShell 发布到正式的 Microsoft 存储库。</span><span class="sxs-lookup"><span data-stu-id="03731-214">PowerShell for Linux is published to official Microsoft repositories for easy installation and updates.</span></span>

```sh
# Register the Microsoft signature key
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc

# Register the Microsoft RedHat repository
curl https://packages.microsoft.com/config/rhel/7/prod.repo | sudo tee /etc/yum.repos.d/microsoft.repo

# Update the list of products
sudo dnf update

# Install a system component
sudo dnf install compat-openssl10

# Install PowerShell
sudo dnf install -y powershell

# Start PowerShell
pwsh
```

### <a name="installation-via-direct-download---fedora-28-29-and-30"></a><span data-ttu-id="03731-215">通过直接下载进行安装 - Fedora 28、Fedora 29 和 Fedora 30</span><span class="sxs-lookup"><span data-stu-id="03731-215">Installation via Direct Download - Fedora 28, 29, and 30</span></span>

<span data-ttu-id="03731-216">从`powershell-7.0.0-1.rhel.7.x86_64.rpm`版本[页中将 Debian 包 ][] 下载到 Fedora 计算机。</span><span class="sxs-lookup"><span data-stu-id="03731-216">Download the RPM package `powershell-7.0.0-1.rhel.7.x86_64.rpm` from the [releases][] page onto the Fedora machine.</span></span>

<span data-ttu-id="03731-217">然后在终端中执行以下命令：</span><span class="sxs-lookup"><span data-stu-id="03731-217">Then, in the terminal, execute the following commands:</span></span>

```sh
sudo dnf install compat-openssl10
sudo dnf install powershell-7.0.0-1.rhel.7.x86_64.rpm
```

<span data-ttu-id="03731-218">无需该中间下载步骤即可安装 RPM：</span><span class="sxs-lookup"><span data-stu-id="03731-218">You can install the RPM without the intermediate step of downloading it:</span></span>

```sh
sudo dnf install compat-openssl10
sudo dnf install https://github.com/PowerShell/PowerShell/releases/download/v7.0.0/powershell-7.0.0-1.rhel.7.x86_64.rpm
```

### <a name="uninstallation---fedora-28-29-and-30"></a><span data-ttu-id="03731-219">卸载 - Fedora 28、Fedora 29 和 Fedora 30</span><span class="sxs-lookup"><span data-stu-id="03731-219">Uninstallation - Fedora 28, 29, and 30</span></span>

```sh
sudo dnf remove powershell
```

## <a name="arch-linux"></a><span data-ttu-id="03731-220">Arch Linux</span><span class="sxs-lookup"><span data-stu-id="03731-220">Arch Linux</span></span>

> [!NOTE]
> <span data-ttu-id="03731-221">Arch 支持不受 Microsoft 的官方支持且由社区维护。</span><span class="sxs-lookup"><span data-stu-id="03731-221">Arch support is not officially supported by Microsoft and is maintained by the community.</span></span>

<span data-ttu-id="03731-222">[Arch Linux][] 用户存储库 (AUR) 中提供有 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="03731-222">PowerShell is available from the [Arch Linux][] User Repository (AUR).</span></span>

* <span data-ttu-id="03731-223">可使用[最新标记版本][arch-release]对其进行编译</span><span class="sxs-lookup"><span data-stu-id="03731-223">It can be compiled with the [latest tagged release][arch-release]</span></span>
* <span data-ttu-id="03731-224">可使用[最新 commit to master][arch-git] 对其进行编译</span><span class="sxs-lookup"><span data-stu-id="03731-224">It can be compiled from the [latest commit to master][arch-git]</span></span>
* <span data-ttu-id="03731-225">可使用[最新版本二进制文件][arch-bin]进行安装</span><span class="sxs-lookup"><span data-stu-id="03731-225">It can be installed using the [latest release binary][arch-bin]</span></span>

<span data-ttu-id="03731-226">AUR 中的包由社区维护，并无正式支持。</span><span class="sxs-lookup"><span data-stu-id="03731-226">Packages in the AUR are community maintained; there's no official support.</span></span>

<span data-ttu-id="03731-227">若要详细了解如何从 AUR 安装包，请参阅 [Arch Linux wiki](https://wiki.archlinux.org/index.php/Arch_User_Repository#Installing_packages) 或[在 Docker 中使用 PowerShell](powershell-in-docker.md)。</span><span class="sxs-lookup"><span data-stu-id="03731-227">For more information on installing packages from the AUR, see the [Arch Linux wiki](https://wiki.archlinux.org/index.php/Arch_User_Repository#Installing_packages) or [Using PowerShell in Docker](powershell-in-docker.md).</span></span>

[Arch Linux]: https://www.archlinux.org/download/
[arch-release]: https://aur.archlinux.org/packages/powershell/
[arch-git]: https://aur.archlinux.org/packages/powershell-git/
[arch-bin]: https://aur.archlinux.org/packages/powershell-bin/

## <a name="snap-package"></a><span data-ttu-id="03731-229">Snap 包</span><span class="sxs-lookup"><span data-stu-id="03731-229">Snap Package</span></span>

### <a name="getting-snapd"></a><span data-ttu-id="03731-230">获取 snapd</span><span class="sxs-lookup"><span data-stu-id="03731-230">Getting snapd</span></span>

<span data-ttu-id="03731-231">需具备 `snapd` 才能运行 Snap。</span><span class="sxs-lookup"><span data-stu-id="03731-231">`snapd` is required to run snaps.</span></span> <span data-ttu-id="03731-232">按照[这些说明](https://docs.snapcraft.io/core/install)确保你已安装 `snapd`。</span><span class="sxs-lookup"><span data-stu-id="03731-232">Use [these instructions](https://docs.snapcraft.io/core/install) to make sure you have `snapd` installed.</span></span>

### <a name="installation-via-snap"></a><span data-ttu-id="03731-233">通过 Snap 进行安装</span><span class="sxs-lookup"><span data-stu-id="03731-233">Installation via Snap</span></span>

<span data-ttu-id="03731-234">为简化安装和更新，已向 [Snap 存储](https://snapcraft.io/store)发布适用于 Linux 的 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="03731-234">PowerShell for Linux is published to the [Snap store](https://snapcraft.io/store) for easy installation and updates.</span></span>

<span data-ttu-id="03731-235">首选方法如下所示：</span><span class="sxs-lookup"><span data-stu-id="03731-235">The preferred method is as follows:</span></span>

```sh
# Install PowerShell
sudo snap install powershell --classic

# Start PowerShell
pwsh
```

<span data-ttu-id="03731-236">若要安装预览版本，请使用以下方法：</span><span class="sxs-lookup"><span data-stu-id="03731-236">To install a preview version, use the following method:</span></span>

```sh
# Install PowerShell
sudo snap install powershell-preview --classic

# Start PowerShell
pwsh-preview
```

<span data-ttu-id="03731-237">安装完成后，Snap 将自动升级。</span><span class="sxs-lookup"><span data-stu-id="03731-237">After installation, Snap will automatically upgrade.</span></span> <span data-ttu-id="03731-238">可以使用 `sudo snap refresh powershell` 或 `sudo snap refresh powershell-preview` 触发升级。</span><span class="sxs-lookup"><span data-stu-id="03731-238">You can trigger an upgrade using `sudo snap refresh powershell` or `sudo snap refresh powershell-preview`.</span></span>

### <a name="uninstallation"></a><span data-ttu-id="03731-239">卸载</span><span class="sxs-lookup"><span data-stu-id="03731-239">Uninstallation</span></span>

```sh
sudo snap remove powershell
```

<span data-ttu-id="03731-240">或</span><span class="sxs-lookup"><span data-stu-id="03731-240">or</span></span>

```sh
sudo snap remove powershell-preview
```

## <a name="kali"></a><span data-ttu-id="03731-241">Kali</span><span class="sxs-lookup"><span data-stu-id="03731-241">Kali</span></span>

> [!NOTE]
> <span data-ttu-id="03731-242">Kali 支持不受 Microsoft 的官方支持且由社区维护。</span><span class="sxs-lookup"><span data-stu-id="03731-242">Kali support is not officially supported by Microsoft and is maintained by the community.</span></span>

### <a name="installation---kali"></a><span data-ttu-id="03731-243">安装 - Kali</span><span class="sxs-lookup"><span data-stu-id="03731-243">Installation - Kali</span></span>

```sh
# Install PowerShell package
apt update && apt -y install powershell

# Start PowerShell
pwsh
```

### <a name="uninstallation---kali"></a><span data-ttu-id="03731-244">卸载 - Kali</span><span class="sxs-lookup"><span data-stu-id="03731-244">Uninstallation - Kali</span></span>

```sh
# Uninstall PowerShell package
apt -y remove powershell
```

## <a name="raspbian"></a><span data-ttu-id="03731-245">Raspbian</span><span class="sxs-lookup"><span data-stu-id="03731-245">Raspbian</span></span>

> [!NOTE]
> <span data-ttu-id="03731-246">Raspbian 支持是实验性的。</span><span class="sxs-lookup"><span data-stu-id="03731-246">Raspbian support is experimental.</span></span>

<span data-ttu-id="03731-247">当前仅 Raspbian Stretch 支持 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="03731-247">Currently, PowerShell is only supported on Raspbian Stretch.</span></span>

<span data-ttu-id="03731-248">CoreCLR 和 PowerShell 仅适用于 Pi 2 和 Pi 3 设备，因为其他设备（如 [Pi 0](https://github.com/dotnet/coreclr/issues/10605)）有不受支持的处理器。</span><span class="sxs-lookup"><span data-stu-id="03731-248">CoreCLR and PowerShell will only work on Pi 2 and Pi 3 devices as other devices, like [Pi Zero](https://github.com/dotnet/coreclr/issues/10605), have an unsupported processor.</span></span>

<span data-ttu-id="03731-249">下载 [Raspbian Stretch](https://www.raspberrypi.org/downloads/raspbian/) 并按照[安装说明](https://www.raspberrypi.org/documentation/installation/installing-images/README.md)操作，将其安装在你的 Pi 上。</span><span class="sxs-lookup"><span data-stu-id="03731-249">Download [Raspbian Stretch](https://www.raspberrypi.org/downloads/raspbian/) and follow the [installation instructions](https://www.raspberrypi.org/documentation/installation/installing-images/README.md) to get it onto your Pi.</span></span>

### <a name="installation---raspbian"></a><span data-ttu-id="03731-250">安装 - Raspbian</span><span class="sxs-lookup"><span data-stu-id="03731-250">Installation - Raspbian</span></span>

```sh
###################################
# Prerequisites

# Update package lists
sudo apt-get update

# Install libunwind8 and libssl1.0
# Regex is used to ensure that we do not install libssl1.0-dev, as it is a variant that is not required
sudo apt-get install '^libssl1.0.[0-9]$' libunwind8 -y

###################################
# Download and extract PowerShell

# Grab the latest tar.gz
wget https://github.com/PowerShell/PowerShell/releases/download/v7.0.0/powershell-7.0.0-linux-arm32.tar.gz

# Make folder to put powershell
mkdir ~/powershell

# Unpack the tar.gz file
tar -xvf ./powershell-7.0.0-linux-arm32.tar.gz -C ~/powershell

# Start PowerShell
~/powershell/pwsh
```

<span data-ttu-id="03731-251">或者，可以创建可启动 PowerShell 的符号链接，而无需指定到 `pwsh` 二进制文件的路径。</span><span class="sxs-lookup"><span data-stu-id="03731-251">Optionally, you can create a symbolic link to start PowerShell without specifying the path to the `pwsh` binary.</span></span>

```sh
# Start PowerShell from bash with sudo to create a symbolic link
sudo ~/powershell/pwsh -c New-Item -ItemType SymbolicLink -Path "/usr/bin/pwsh" -Target "$PSHOME/pwsh" -Force

# alternatively you can run following to create a symbolic link
# sudo ln -s ~/powershell/pwsh /usr/bin/pwsh

# Now to start PowerShell you can just run "pwsh"
```

### <a name="uninstallation---raspbian"></a><span data-ttu-id="03731-252">卸载 - Raspbian</span><span class="sxs-lookup"><span data-stu-id="03731-252">Uninstallation - Raspbian</span></span>

```sh
rm -rf ~/powershell
```

## <a name="install-as-a-net-global-tool"></a><span data-ttu-id="03731-253">作为 .NET 全局工具安装</span><span class="sxs-lookup"><span data-stu-id="03731-253">Install as a .NET Global tool</span></span>

<span data-ttu-id="03731-254">如果你已安装 [.NET Core SDK](/dotnet/core/sdk)，则可以轻松地安装 PowerShell 作为 [.NET 全局工具](/dotnet/core/tools/global-tools)。</span><span class="sxs-lookup"><span data-stu-id="03731-254">If you already have the [.NET Core SDK](/dotnet/core/sdk) installed, it's easy to install PowerShell as a [.NET Global tool](/dotnet/core/tools/global-tools).</span></span>

```
dotnet tool install --global PowerShell
```

<span data-ttu-id="03731-255">dotnet 工具安装程序将 `~/.dotnet/tools` 添加到 `PATH` 环境变量中。</span><span class="sxs-lookup"><span data-stu-id="03731-255">The dotnet tool installer adds `~/.dotnet/tools` to your `PATH` environment variable.</span></span> <span data-ttu-id="03731-256">但是，当前运行的 shell 没有更新的 `PATH`。</span><span class="sxs-lookup"><span data-stu-id="03731-256">However, the currently running shell does not have the updated `PATH`.</span></span> <span data-ttu-id="03731-257">应该可以通过键入 `pwsh` 从新 shell 启动 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="03731-257">You should be able to start PowerShell from a new shell by typing `pwsh`.</span></span>

## <a name="binary-archives"></a><span data-ttu-id="03731-258">二进制存档</span><span class="sxs-lookup"><span data-stu-id="03731-258">Binary Archives</span></span>

<span data-ttu-id="03731-259">已对 Linux 平台提供 PowerShell 二进制 `tar.gz` 存档，以启用高级部署方案。</span><span class="sxs-lookup"><span data-stu-id="03731-259">PowerShell binary `tar.gz` archives are provided for Linux platforms to enable advanced deployment scenarios.</span></span>

### <a name="dependencies"></a><span data-ttu-id="03731-260">依赖项</span><span class="sxs-lookup"><span data-stu-id="03731-260">Dependencies</span></span>

<span data-ttu-id="03731-261">PowerShell 为所有 Linux 分发版生成可移植二进制文件。</span><span class="sxs-lookup"><span data-stu-id="03731-261">PowerShell builds portable binaries for all Linux distributions.</span></span> <span data-ttu-id="03731-262">但是对于不同的分发版，.NET Core 运行时需要不同的依赖项，并且 PowerShell 也有相同要求。</span><span class="sxs-lookup"><span data-stu-id="03731-262">But, .NET Core runtime requires different dependencies on different distributions, and PowerShell does too.</span></span>

<span data-ttu-id="03731-263">下表列出了在不同 Linux 分发版上正式支持的 .NET Core 2.0 依赖项。</span><span class="sxs-lookup"><span data-stu-id="03731-263">The following chart shows the .NET Core 2.0 dependencies that are officially supported on different Linux distributions.</span></span>

| <span data-ttu-id="03731-264">OS</span><span class="sxs-lookup"><span data-stu-id="03731-264">OS</span></span>                 | <span data-ttu-id="03731-265">依赖项</span><span class="sxs-lookup"><span data-stu-id="03731-265">Dependencies</span></span> |
| ------------------ | ------------ |
| <span data-ttu-id="03731-266">Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="03731-266">Ubuntu 16.04</span></span>       | <span data-ttu-id="03731-267">libc6、libgcc1、libgssapi-krb5-2、liblttng-ust0、libstdc++6、</span><span class="sxs-lookup"><span data-stu-id="03731-267">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="03731-268">libcurl3、libunwind8、libuuid1、zlib1g、libssl1.0.0、libicu55</span><span class="sxs-lookup"><span data-stu-id="03731-268">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu55</span></span> |
| <span data-ttu-id="03731-269">Ubuntu 17.10</span><span class="sxs-lookup"><span data-stu-id="03731-269">Ubuntu 17.10</span></span>       | <span data-ttu-id="03731-270">libc6、libgcc1、libgssapi-krb5-2、liblttng-ust0、libstdc++6、</span><span class="sxs-lookup"><span data-stu-id="03731-270">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="03731-271">libcurl3、libunwind8、libuuid1、zlib1g、libssl1.0.0、libicu57</span><span class="sxs-lookup"><span data-stu-id="03731-271">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu57</span></span> |
| <span data-ttu-id="03731-272">Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="03731-272">Ubuntu 18.04</span></span>       | <span data-ttu-id="03731-273">libc6、libgcc1、libgssapi-krb5-2、liblttng-ust0、libstdc++6、</span><span class="sxs-lookup"><span data-stu-id="03731-273">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="03731-274">libcurl3、libunwind8、libuuid1、zlib1g、libssl1.0.0、libicu60</span><span class="sxs-lookup"><span data-stu-id="03731-274">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu60</span></span> |
| <span data-ttu-id="03731-275">Debian 8 (Jessie)</span><span class="sxs-lookup"><span data-stu-id="03731-275">Debian 8 (Jessie)</span></span>  | <span data-ttu-id="03731-276">libc6、libgcc1、libgssapi-krb5-2、liblttng-ust0、libstdc++6、</span><span class="sxs-lookup"><span data-stu-id="03731-276">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="03731-277">libcurl3、libunwind8、libuuid1、zlib1g、libssl1.0.0、libicu52</span><span class="sxs-lookup"><span data-stu-id="03731-277">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu52</span></span> |
| <span data-ttu-id="03731-278">Debian 9 (Stretch)</span><span class="sxs-lookup"><span data-stu-id="03731-278">Debian 9 (Stretch)</span></span> | <span data-ttu-id="03731-279">libc6、libgcc1、libgssapi-krb5-2、liblttng-ust0、libstdc++6、</span><span class="sxs-lookup"><span data-stu-id="03731-279">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="03731-280">libcurl3、libunwind8、libuuid1、zlib1g、libssl1.0.2、libicu57</span><span class="sxs-lookup"><span data-stu-id="03731-280">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.2, libicu57</span></span> |
| <span data-ttu-id="03731-281">CentOS 7</span><span class="sxs-lookup"><span data-stu-id="03731-281">CentOS 7</span></span> <br> <span data-ttu-id="03731-282">Oracle Linux 7</span><span class="sxs-lookup"><span data-stu-id="03731-282">Oracle Linux 7</span></span> <br> <span data-ttu-id="03731-283">RHEL 7</span><span class="sxs-lookup"><span data-stu-id="03731-283">RHEL 7</span></span> | <span data-ttu-id="03731-284">libunwind、libcurl、openssl-libs、libicu</span><span class="sxs-lookup"><span data-stu-id="03731-284">libunwind, libcurl, openssl-libs, libicu</span></span> |
| <span data-ttu-id="03731-285">openSUSE 42.3</span><span class="sxs-lookup"><span data-stu-id="03731-285">openSUSE 42.3</span></span> | <span data-ttu-id="03731-286">libcurl4、libopenssl1_0_0、libicu52_1</span><span class="sxs-lookup"><span data-stu-id="03731-286">libcurl4, libopenssl1_0_0, libicu52_1</span></span> |
| <span data-ttu-id="03731-287">openSUSE Leap 15</span><span class="sxs-lookup"><span data-stu-id="03731-287">openSUSE Leap 15</span></span> | <span data-ttu-id="03731-288">libcurl4、libopenssl1_0_0、libicu60_2</span><span class="sxs-lookup"><span data-stu-id="03731-288">libcurl4, libopenssl1_0_0, libicu60_2</span></span> |
| <span data-ttu-id="03731-289">Fedora 27</span><span class="sxs-lookup"><span data-stu-id="03731-289">Fedora 27</span></span> <br> <span data-ttu-id="03731-290">Fedora 28</span><span class="sxs-lookup"><span data-stu-id="03731-290">Fedora 28</span></span> | <span data-ttu-id="03731-291">libunwind、libcurl、openssl-libs、libicu、compat-openssl10</span><span class="sxs-lookup"><span data-stu-id="03731-291">libunwind, libcurl, openssl-libs, libicu, compat-openssl10</span></span> |

<span data-ttu-id="03731-292">若要在不受正式支持的 Linux 分发版上部署 PowerShell 二进制文件，则需在各个步骤中安装目标 OS 的必要依赖项。</span><span class="sxs-lookup"><span data-stu-id="03731-292">To deploy PowerShell binaries on Linux distributions that aren't officially supported, you need to install the necessary dependencies for the target OS in separate steps.</span></span> <span data-ttu-id="03731-293">例如，[Amazon Linux dockerfile][amazon-dockerfile] 先安装依赖项，然后提取 Linux `tar.gz` 存档。</span><span class="sxs-lookup"><span data-stu-id="03731-293">For example, our [Amazon Linux dockerfile][amazon-dockerfile] installs dependencies first, and then extracts the Linux `tar.gz` archive.</span></span>

[amazon-dockerfile]: https://github.com/PowerShell/PowerShell-Docker/blob/master/release/community-stable/amazonlinux/docker/Dockerfile

### <a name="installation---binary-archives"></a><span data-ttu-id="03731-294">安装 - 二进制存档</span><span class="sxs-lookup"><span data-stu-id="03731-294">Installation - Binary Archives</span></span>

#### <a name="linux"></a><span data-ttu-id="03731-295">Linux</span><span class="sxs-lookup"><span data-stu-id="03731-295">Linux</span></span>

```sh
# Download the powershell '.tar.gz' archive
curl -L -o /tmp/powershell.tar.gz https://github.com/PowerShell/PowerShell/releases/download/v7.0.0/powershell-7.0.0-linux-x64.tar.gz

# Create the target folder where powershell will be placed
sudo mkdir -p /opt/microsoft/powershell/7

# Expand powershell to the target folder
sudo tar zxf /tmp/powershell.tar.gz -C /opt/microsoft/powershell/7

# Set execute permissions
sudo chmod +x /opt/microsoft/powershell/7/pwsh

# Create the symbolic link that points to pwsh
sudo ln -s /opt/microsoft/powershell/7/pwsh /usr/bin/pwsh
```

### <a name="uninstalling-binary-archives"></a><span data-ttu-id="03731-296">卸载二进制存档</span><span class="sxs-lookup"><span data-stu-id="03731-296">Uninstalling binary archives</span></span>

```sh
sudo rm -rf /usr/bin/pwsh /opt/microsoft/powershell
```

## <a name="paths"></a><span data-ttu-id="03731-297">路径</span><span class="sxs-lookup"><span data-stu-id="03731-297">Paths</span></span>

- <span data-ttu-id="03731-298">`$PSHOME` 是 `/opt/microsoft/powershell/7/`</span><span class="sxs-lookup"><span data-stu-id="03731-298">`$PSHOME` is `/opt/microsoft/powershell/7/`</span></span>
- <span data-ttu-id="03731-299">将从 `~/.config/powershell/profile.ps1` 中读取用户配置文件</span><span class="sxs-lookup"><span data-stu-id="03731-299">User profiles will be read from `~/.config/powershell/profile.ps1`</span></span>
- <span data-ttu-id="03731-300">将从 `$PSHOME/profile.ps1` 中读取默认配置文件</span><span class="sxs-lookup"><span data-stu-id="03731-300">Default profiles will be read from `$PSHOME/profile.ps1`</span></span>
- <span data-ttu-id="03731-301">将从 `~/.local/share/powershell/Modules` 中读取用户模块</span><span class="sxs-lookup"><span data-stu-id="03731-301">User modules will be read from `~/.local/share/powershell/Modules`</span></span>
- <span data-ttu-id="03731-302">将从 `/usr/local/share/powershell/Modules` 中读取共享模块</span><span class="sxs-lookup"><span data-stu-id="03731-302">Shared modules will be read from `/usr/local/share/powershell/Modules`</span></span>
- <span data-ttu-id="03731-303">将从 `$PSHOME/Modules` 中读取默认模块</span><span class="sxs-lookup"><span data-stu-id="03731-303">Default modules will be read from `$PSHOME/Modules`</span></span>
- <span data-ttu-id="03731-304">PSReadline 历史记录将记录到 `~/.local/share/powershell/PSReadLine/ConsoleHost_history.txt`</span><span class="sxs-lookup"><span data-stu-id="03731-304">PSReadline history will be recorded to `~/.local/share/powershell/PSReadLine/ConsoleHost_history.txt`</span></span>

<span data-ttu-id="03731-305">配置文件采用 PowerShell 的按主机配置，所以默认主机特定配置文件位于相同位置下的 `Microsoft.PowerShell_profile.ps1` 中。</span><span class="sxs-lookup"><span data-stu-id="03731-305">The profiles respect PowerShell's per-host configuration, so the default host-specific profiles exists at `Microsoft.PowerShell_profile.ps1` in the same locations.</span></span>

<span data-ttu-id="03731-306">PowerShell 采用 Linux 上的 [XDG 基目录规范][xdg-bds]。</span><span class="sxs-lookup"><span data-stu-id="03731-306">PowerShell respects the [XDG Base Directory Specification][xdg-bds] on Linux.</span></span>

[页中将 Debian 包 ]: https://github.com/PowerShell/PowerShell/releases/latest
[releases]: https://github.com/PowerShell/PowerShell/releases/latest
[xdg-bds]: https://specifications.freedesktop.org/basedir-spec/basedir-spec-latest.html

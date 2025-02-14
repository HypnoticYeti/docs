---
Order: 10
xref: gui-installation
Title: Installation
Description: Instructions on how to install Chocolatey GUI
RedirectFrom:
  - en-us/chocolatey-gui/setup/installation/chocolateygui
  - en-us/chocolatey-gui/setup/installation/chocolatey-gui
---

The easiest way to install Chocolatey GUI is to use Chocolatey.  Use the
following command to install the latest version of Chocolatey GUI:

```powershell
choco install chocolateygui
```

## Upgrading Chocolatey GUI

If you already have Chocolatey GUI installed, you can upgrade to the latest
version using the following command:

```powershell
choco upgrade chocolateygui
```

## Installing Beta Versions of Chocolatey GUI

Each time a commit is made into the Chocolatey GUI repository, a build is
performed, and the output is pushed to the Chocolatey GUI MyGet feed.  If you
are interested in using the very latest version of Chocolatey GUI, you can use
the following command to install it:

```powershell
choco upgrade chocolateygui --pre --source="'https://myget.org/f/chocolateygui'"
```

 ## Package Parameters

The following package parameters can be passed into the `choco install` or `choco upgrade` command to control how the installed version of Chocolatey GUI is configured.

* `/Global` - Should the configuration change be applied globally, or for the current user.
* `/ShowConsoleOutput` - Enables/disables whether or not Chocolatey GUI shows output from the commands being executed when a job is running.
* `/DefaultToTileViewForLocalSource` - Enables/disables whether or not Chocolatey GUI defaults to tile instead of list view for the local source view.
* `/DefaultToTileViewForRemoteSource` - Enables/disables whether or not Chocolatey GUI defaults to tile instead of list view for all remote source views.
* `/UseDelayedSearch` - Enables/disables whether or not Chocolatey GUI uses a live search, which returns results after a short delay without clicking the search button.
* `/PreventPreload` - Prevents preloading results with a blank search when opening the remote source view.
* `/PreventAutomatedOutdatedPackagesCheck` - Prevents automated check for outdated packages on startup.
* `/ExcludeInstalledPackages` - Enables/disables whether or not Chocolatey GUI shows packages that are already installed when viewing sources.
* `/ShowAggregatedSourceView` - Enables/disables whether or not Chocolatey GUI shows an additional source combining all sources into one location.
* `/ShowAdditionalPackageInformation` - Show additional package information on Local and Remote views.
* `/AllowNonAdminAccessToSettings` - Controls whether or not a non-administrator user can access the Settings Screen. NOTE: This feature will only work with Chocolatey for Business and the Chocolatey GUI licensed extension installed.
* `/UseKeyboardBindings` - Allows keyboard bindings to be used to interact with different areas of the Chocolatey GUI User Interface.
* `/HidePackageDownloadCount` - Allows keyboard bindings to be used to interact with different areas of the Chocolatey GUI User Interface.
* `/PreventAllPackageIconDownloads` - Enables/disables whether Chocolatey GUI will attempt to download the icons for packages. NOTE: This feature will only work with Chocolatey for Business and the Chocolatey GUI licensed extension installed.
* `/HideAllRemoteChocolateySources` - Enable/disables whether or not all remote sources are hidden - essentially enabling a read-only view of installed packages. NOTE: This feature will only work with Chocolatey for Business and the Chocolatey GUI licensed extension installed.
* `/DefaultToDarkMode` - Enables/disables whether or not Chocolatey GUI defaults to using dark mode for the Chocolatey GUI User Interface.
* `/OutdatedPackagesCacheDurationInMinutes` - The length of time, in minutes, which Chocolatey GUI will wait before invalidating the cached result of outdated packages for the machine.
* `/DefaultSourceName` - The name of the source which should be shown by default when opening application. NOTE: This configuration setting will only work with Chocolatey for Business and the Chocolatey GUI licensed extension installed.
* `/HideThisPCSource` - Enable/disables whether or not This PC source is hidden. NOTE: This feature will only work with Chocolatey for Business and the Chocolatey GUI licensed extension installed.
* `/PreventUsageOfUpdateAllButton` - Enables/disables whether the Update All button is visible. NOTE: This feature will only work with Chocolatey for Business and the Chocolatey GUI licensed extension installed.

As an example, the following installation command could be used to enable ShowConsoleOutput to ensure UseDelayedSearch is disabled, and set the output cache to 120 minutes:

```
choco install chocolateygui --params="'/ShowConsoleOutput=$true /UseDelayedSearch=$false /OutdatedPackagesCacheDurationInMinutes=120'"
```

If you wanted to set these options globally so that all users on the machine got these values, run the following:

```
choco install chocolateygui --params="'/ShowConsoleOutput=$true /UseDelayedSearch=$false /OutdatedPackagesCacheDurationInMinutes=120 /Global'"
```
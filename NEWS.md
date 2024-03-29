# svKomodo 1.0.0

-   README.md file added.

-   NEWS file reworked to use the Markdown format.

-   Man pages are rewritten in Roxygen2.

-   Pkgdown web site added, spelling, and R CMD check GitHub actions.

# svKomodo 0.9-63

-   Starting from R revision \>= 67550, the HTML help port is now retrieved using `tools::startDynamicHelp(NA)`.

# svKomodo 0.9-62

-   Author field rebuild in DESCRIPTION file

-   `.onAttach()` reworked to eliminate `:::` (not allowed by CRAN)

-   `utils::rc.settings` are adjusted in `.onAttach()` and restored in `.onUnload()`

# svKomodo 0.9-61

-   Simplification of internal code to get Komodo location. It does not require a specific version of 'locate' on Unix/Linux any more.

# svKomodo 0.9-60

-   `.onAttach()` is reworked for not issuing warning messages in Mac OS X.

# svKomodo 0.9-59

-   R is now configured to be used with SciViews Komodo (Komodo Edit + SciViews-K) when the package is attached. It was previously configured when it was loaded.

-   Temporary objects are now stored in `SciViews:TempEnv` instead of `TempEnv` and consequently, svMisc \>= 0.9-68 is needed.

-   Further protection before looking for komodo with locate: (1) if locate is not there, do not try to use it, and (2) do not use it on Mac OS X.

# svKomodo 0.9-58

-   The package was not loading correctly when not on `.libPaths`. Fixed.

# svKomodo 0.9-57

-   svKomodo creates now at loading a `.Last.sys()` function in `SciViews:TempEnv` indicating to Komodo Edit that R has quit. This is required to update R menus there.

-   The SciViews-K configuration file is not saved from here anymore (CRAN now does not accept packages that write files elsewhere than in R temp dir). This configuration file is now created by the SciViews-K Komodo plugin, in svStart.R.

# svKomodo 0.9-56

-   NEWS file reworked to use the new Rd format.

# svKomodo 0.9-55

-   On some machines, `system("locate Komodo ...")` fails. Added some more checking in this situation.

-   In `.onLoad()`, slight reworking of the `svPager()` function to avoid calling `.Internal(file.show(....))`.

# svKomodo 0.9-54

-   Startup code is changed... a part of the code in svStart.R in the SciViews-K plugin is now executed here!

-   Save and load SciViews config in `~/.SciViewsConfig.RData` file, so that it is possible to reconfigure R for SciViews just by reloading the present package.

# svKomodo 0.9-53

-   `koCmd()` can now use either socket or file for communication with Komodo.

# svKomodo 0.9-52

-   The package is created from svGUI 0.9-51 (functions that concern interaction with Komodo Edit/IDE). `guiInstall()`, `guiUninstall()`, `guiRefresh()` & `guiAutoRefresh()` are also renamed `koXXX()`, in order to better match their purpose (to communicate with Komodo Edit/IDE only), while the previous implementation was intended for more general purpose. Since, it was never used elsewhere, narrowing its scope allows to simplify the code greatly!

-   The callback mechanism to run commands from a client is now moved from svSocket package to here, so that it can also be used in the svHttp package.

-   `koRefresh()` now looks at the "changed" attribute of the object returned by `objList()`, and so, can make the difference between "no changes", and "changes, but the environment go no more objects".

-   Here under is a transcript of svGUI before functions are moved to svKomodo:

-   `koCmd()` now should prepend \<\<<js>\>\> to the JavaScript code to get it evaluated in Komodo (starting with SciViews-K 0.9-18). Komodo now also accepts RJsonP strings, prepended with \<\<<rjson>\>\>. If there is no code prepended to the string send to Komodo, it is just printed in the local R console. A new 'type' argument specifies what kind of string we send to Komodo. [in svGUI 0.9-48]

-   Use of `svTaskCallbackManager()` of svSocket \>= 0.9-48 to register task callback that are also executed after each R code send by socket clients. [in svGUI 0.9-46]

-   `guiRefresh()` now clears active items and MRU lists in Komodo for non-defined active data frames and lm objects. [in svGUI 0.9-46]

-   Added `guiRefresh()` and `guiAutoRefresh()` to refresh automatically the content of the GUI (Komodo) object explorer and the lists of active objects. [in svGUI 0.9-45]

-   Preparation for CRAN submission: polishing the package. [in svGUI 0.9-44]

-   Made compatible with R 2.6.x (previous version was compatible with R 2.7.0). [in svGUI 0.9-43]

-   `koCmd()` is now more robust and do not issue a warning or an error if the Komodo server is not available (but the error message is returned by the function with a 'try-error' class, so that it can be processed by the caller). [in svGUI 0.9-42]

-   Correction of a bug in the first example of `koCmd()`. [in svGUI 0.9-41]

-   `guiInstall()` now creates a hook to `koCmd()`: `.koCmd()` in `SciViews:TempEnv`. [in svGUI 0.9-41]

-   First version distributed on R-forge. It is completely refactored from older versions (on CRAN since 2003) to make it run with SciViews-K and Komodo Edit (Tinn-R is also supported, but not SciViews-R Console any more). [in svGUI 0.9-40]

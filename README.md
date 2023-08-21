# aseprite-window-x64-builder
*beware, that this was translated with AI, so there may be mistakes, if so you can tell me. Any mentions of I or me in the following text is by the original creator(but translated) of this workflow.*
  This is an automated workflow for two GitHub Actions, to automatically or semi-automatically build x64-bit Aseprite for Windows.
By using GitHub Actions, no manual compilation is required.
# Read, review & be aware that you agree with it by downloading, using the software. [Aseprite 的 EULA](https://github.com/aseprite/aseprite/blob/main/EULA.txt).
  In order to comply with Aseprite's EULA, this workflow will not upload the compiled binaries to public accessible space. The compiled binaries will be stored in the `draft` of `Releases` only visible to the repository owner.
  The compiled binary file cannot run normally due to the lack of `libcrypto-1_1-x64.dll`. Currently, I don’t know how to solve it when compiling. The workflow will be from <https://github.com/feenkcom/libopenssl/releases >Get the missing dll and package it together. If not needed, you can replace, delete or modify the workflow according to the situation.

# Instructions

  Fork this repository, open the `Setting-Actions-General` page of the Fork repository, make sure `Workflow permissions` select `Read and write permissions`.

## Build Manually

  Visit <https://github.com/aseprite/aseprite/releases>, and get the `tags` corresponding to the `Release` you want to build. Then open the `Actions` page of the Fork repository, select `manually build` workflow on the left, and click` Run workflow` and then fill in the `tags` just obtained under the prompt corresponding to `Release tags`, click `Run workflow` and wait for `workflow` to be executed. Open the `Code-Releases` of the Fork repository, in the ` Download from the attachment below draft`.

## Automatically check for updates and builds

  If the current version of the Fork repository is different from the latest Releases of Aseprite, it will automatically get the latest tags and then perform compilation and generate `draft` in `Code-Releases` of the Fork repository.

`Automatically check for updates and build` workflow will be executed automatically at `0:00` UTC (Coordinated Universal Time) and `8:00` Beijing time (UTC+8), please edit `.github/workflows/ if you want to enable it auto-build.yml`, uncomment the third to fifth lines:
~~~
on:
  schedule:
  - cron: '0 0 * * *'
~~~

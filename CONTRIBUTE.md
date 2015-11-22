Contributing to Atom

source du document: https://github.com/atom/atom/blob/master/CONTRIBUTING.md

:+1::tada: First off, thanks for taking the time to contribute! :tada::+1:

The following is a set of guidelines for contributing to Atom and its packages, which are hosted in the Atom Organization on GitHub. These are just guidelines, not rules, use your best judgment and feel free to propose changes to this document in a pull request.
Table Of Contents

What should I know before I get started?

    Code of Conduct
    Atom and Packages

How Can I Contribute?

    Reporting Bugs
    Your First Code Contribution
    Pull Requests

Styleguides

    Git Commit Messages
    CoffeeScript Styleguide
    Specs Styleguide
    Documentation Styleguide

Additional Notes

    Issue and Pull Request Labels

What should I know before I get started?
Code of Conduct

This project adheres to the Contributor Covenant 1.2. By participating, you are expected to uphold this code. Please report unacceptable behavior to atom@github.com.
Atom and Packages

Atom is a large open source project—it's made up of over 200 repositories. When you initially consider contributing to Atom, you might be unsure about which of those 200 repositories implements the functionality you want to change or report a bug for. This section should help you with that.

Atom is intentionally very modular. Nearly every non-editor UI element you interact with comes from a package, even fundamental things like tabs and the status-bar. These packages are packages in the same way that packages in the package store are packages, with one difference: they are bundled into the default distribution.

atom-packages

To get a sense for the packages that are bundled with Atom, you can go to Settings > Packages within Atom and take a look at the Core Packages section.

Here's a list of the big ones:

    atom/atom - Atom Core! The core editor component is responsible for basic text editing (e.g. cursors, selections, scrolling), text indentation, wrapping, and folding, text rendering, editor rendering, file system operations (e.g. saving), and installation and auto-updating. You should also use this repository for feedback related to the core API and for large, overarching design proposals.
    tree-view - file and directory listing on the left of the UI.
    fuzzy-finder - the quick file opener.
    find-and-replace - all search and replace functionality.
    tabs - the tabs for open editors at the top of the UI.
    status-bar - the status bar at the bottom of the UI.
    markdown-preview - the rendered markdown pane item.
    settings-view - the settings UI pane item.
    autocomplete-plus - autocompletions shown while typing. Some languages have additional packages for autocompletion functionality, such as autocomplete-html.
    git-diff - Git change indicators shown in the editor's gutter.
    language-javascript - all bundled languages are packages too, and each one has a separate package language-[name]. Use these for feedback on syntax highlighting issues that only appear for a specific language.
    one-dark-ui - the default UI styling for anything but the text editor. UI theme packages (i.e. packages with a -ui suffix) provide only styling and it's possible that a bundled package is responsible for a UI issue. There are other other bundled UI themes, such as one-light-ui.
    one-dark-syntax - the default syntax highlighting styles applied for all languages. There are other other bundled syntax themes, such as solarized-dark. You should use these packages for reporting issues that appear in many languages, but disappear if you change to another syntax theme.
    apm - the apm command line tool (Atom Package Manager). You should use this repository for any contributions related to the apm tool and to publishing packages.
    atom.io - the repository for feedback on the Atom.io website and the Atom.io package API used by apm.

There are many more, but this list should be a good starting point. For more information on how to work with Atom's official packages, see Contributing to Atom Packages.

Also, because Atom is so extensible, it's possible that a feature you've become accustomed to in Atom or an issue you're encountering aren't coming from a bundled package at all, but rather a community package you've installed. Each community package has its own repository too, and you should be able to find it in Settings > Packages for the packages you installed and contribute there.
How Can I Contribute?
Reporting Bugs

This section guides you through submitting a bug report for Atom. Following these guidelines helps maintainers and the community understand your report :pencil:, reproduce the behavior :computer: :computer:, and find related reports :mag_right:.

Before creating bug reports, please check this list as you might find out that you don't need to create one. When you are creating a bug report, please include as many details as possible. If you'd like, you can use this template to structure the information.
Before Submitting A Bug Report

    Check the debugging guide. You might be able to find the cause of the problem and fix things yourself. Most importantly, check if you can reproduce the problem in the latest version of Atom, if the problem happens when you run Atom in safe mode, and if you can get the desired behavior by changing Atom's or packages' config settings.
    Check the FAQs on the forum for a list of common questions and problems.
    Determine which repository the problem should be reported in.
    Perform a cursory search to see if the problem has already been reported. If it has, add a comment to the existing issue instead of opening a new one.

How Do I Submit A (Good) Bug Report?

Bugs are tracked as GitHub issues. After you've determined which repository your bug is related to, create an issue on that repository and provide the following information.

Explain the problem and include additional details to help maintainers reproduce the problem:

    Use a clear and descriptive title for the issue to identify the problem.
    Describe the exact steps which reproduce the problem in as many details as possible. For example, start by explaining how you started Atom, e.g. which command exactly you used in the terminal, or how you started Atom otherwise. When listing steps, don't just say what you did, but explain how you did it. For example, if you moved the cursor to the end of a line, explain if you used the mouse, or a keyboard shortcut or an Atom command, and if so which one?
    Provide specific examples to demonstrate the steps. Include links to files or GitHub projects, or copy/pasteable snippets, which you use in those examples. If you're providing snippets in the issue, use Markdown code blocks.
    Describe the behavior you observed after following the steps and point out what exactly is the problem with that behavior.
    Explain which behavior you expected to see instead and why.
    Include screenshots and animated GIFs which show you following the described steps and clearly demonstrate the problem. If you use the keyboard while following the steps, record the GIF with the Keybinding Resolver shown. You can use this tool to record GIFs on OSX and Windows, and this tool or this tool on Linux.
    If you're reporting that Atom crashed, include a crash report with a stack trace from the operating system. On OSX, the crash report will be available in Console.app under "Diagnostic and usage information" > "User diagnostic reports". Include the crash report in the issue in a code block, a file attachment, or put it in a gist and provide link to that gist.
    If the problem is related to performance, include a CPU profile capture and a screenshot with your report.
    If the Chrome's developer tools pane is shown without you triggering it, that normally means that an exception was thrown. The Console tab will include an entry for the exception. Expand the exception so that the stack trace is visible, and provide the full exception and stack trace in a code blocks and as a screenshot.
    If the problem wasn't triggered by a specific action, describe what you were doing before the problem happened and share more information using the guidelines below.

Provide more context by answering these questions:

    Can you reproduce the problem in safe mode?
    Did the problem start happening recently (e.g. after updating to a new version of Atom) or was this always a problem?
    If the problem started happening recently, can you reproduce the problem in an older version of Atom? What's the most recent version in which the problem doesn't happen? You can download older versions of Atom from the releases page.
    Can you reliably reproduce the issue? If not, provide details about how often the problem happens and under which conditions it normally happens.
    If the problem is related to working with files (e.g. opening and editing files), does the problem happen for all files and projects or only some? Does the problem happen only when working with local or remote files (e.g. on network drives), with files of a specific type (e.g. only JavaScript or Python files), with large files or files with very long lines, or with files in a specific encoding? Is there anything else special about the files you are using?

Include details about your configuration and environment:

    Which version of Atom are you using? You can get the exact version by running atom -v in your terminal, or by starting Atom and running the Application: About command from the Command Palette.
    What's the name and version of the OS you're using?
    Are you running Atom in a virtual machine? If so, which VM software are you using and which operating systems and versions are used for the host and the guest?
    Which packages do you have installed? You can get that list by running apm list -
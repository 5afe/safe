# safe
Repo to collect Gnosis Safe ideas, feature requests and epics in order to make the roadmap more clear

# Creating a specification

Copy the `specs/_template` folder with all contents into a new folder and name it after the specification title,
lowercased, with underscores_instead_of_spaces.

We use `reStructuredText` for the specification documentation as at the moment it is more powerful, standardised and suited better for documneting software than the markdown format.

Where to put what:
- Put UI images into screens/platform subdirectories.
- Describe use case scenarios in the 01_main.rst document.
- You will find further information in other files in the _template directory.

When you have a core of your draft ready, submit a pull-request with a `[WIP]` in the title, and include other people to specification writing, user interface design and so on.

After you specified 20% of the requirements that cover 80% of work, you can put the specification in review,
unless you explicitly want to finalize everything before moving forward to development.

Merged specifications considered ready for planning future releases and starting the development.

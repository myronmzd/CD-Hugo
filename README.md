# CD-Hugo
Since Hugo generates static HTML files, it is easy to deploy using CD pipelines.


Step 1: Determine the Latest Version
Visit Hugo’s Releases on GitHub to find the latest version. For this example, we’ll assume the version is v0.112.5 and that you want the extended version for Linux (64-bit).

On Windows, you can also install Hugo via winget or Chocolatey:
Using winget:
```powershell
winget install Hugo.Hugo
```
Using Chocolatey:
```powershell
choco install hugo-extended -y
```

Step 2: Download the Binary
Run the following command to download the tarball (adjust the version if needed):

```sh
curl -L https://github.com/gohugoio/hugo/releases/download/v0.112.5/hugo_extended_0.112.5_Linux-64bit.tar.gz -o hugo.tar.gz
```
Step 3: Extract the Tarball
Extract the downloaded archive:

```sh
tar -xzf hugo.tar.gz
```
This should create a file named hugo.

Step 4: Move Hugo to Your PATH
Move the binary to a directory that’s in your PATH (for example, /usr/local/bin):

```sh
sudo mv hugo /usr/local/bin/
```
If you don’t have sudo privileges or prefer a local installation, move it to a directory you control and update your PATH accordingly.

Step 5: Verify the Installation
Confirm that Hugo is installed by checking its version:

```sh
hugo version
```

Step 4: to use Hugo for generating your site or building your project, you can run commands like:

```sh
hugo new site my-website
hugo server -D
```
Navigate to the New Site Directory:
Change your directory to the new Hugo site:


## Primary Hugo Commands
hugo new site <directory>
Creates a brand-new Hugo site by generating the default folder structure (including folders like content, layouts, static, etc.) and a configuration file.
Example:

```powershell
hugo new site my-website
hugo new <content-path>
```
Creates a new content file (for example, a new blog post or page) inside your site. The file is pre-populated with front matter.
Example:

```powershell
hugo new posts/my-first-post.md
```
hugo server [flags]
Launches a local development server that builds your site in memory, watches for changes, and provides live reload functionality. Common flags include:

-D or --buildDrafts: Include draft content.
-E or --buildExpired: Include expired content.
-F or --buildFuture: Include future-dated content.
Example:
```powershell
hugo server -D
hugo
```
With no subcommand, Hugo builds your site and writes the generated files to the output directory (by default, the public folder). This is the command you use when you’re ready to generate your final site.
Example:

```powershell
hugo
hugo version
```
Displays the current Hugo version along with build information.
Example:

```powershell
hugo version
hugo help [command]
```
Provides detailed help for a specific command. For example, to get help with the server command:

```powershell
hugo help server
```
Additional Commands
hugo convert config
Converts your site’s configuration file between formats (e.g., from TOML to YAML or JSON).
Example:

```powershell
hugo convert config --from toml --to yaml
hugo import
```
Hugo can import content from other formats or CMS exports (for example, a WordPress export file). The exact syntax may vary depending on the source format.
Example:

```powershell
hugo import wordpress path/to/wordpress-export.xml
hugo list
```
Although not as widely used, Hugo provides subcommands to list content in various states. For example, you can list all draft or future pages:

```powershell
hugo list drafts
hugo list future
```
Using Flags
In addition to the commands above, Hugo provides numerous flags that can be combined with these commands to customize behavior. For instance, when building your site, you can control:

The destination directory with -d or --destination.
The environment with -e or --environment.
The content source folder with -s or --source.
And many others (see the output of hugo help for the full list).
Summary
Create a new site: hugo new site my-website
Create new content: hugo new posts/my-first-post.md
Run a development server: hugo server -D
Build the site: hugo
Display version info: hugo version
Get help for commands: hugo help <command>
Convert configuration files: hugo convert config
Import external content: hugo import wordpress <file>
List content by state: hugo list drafts or hugo list future
By using these commands—and their associated flags—you have full control over creating, developing, and deploying your Hugo site. If you need more detailed usage for any command, running the help command (e.g., hugo help server) will provide additional guidance.
Once inside the site directory, start the local development server with:

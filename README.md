
# SVN Workflow for Managing WordPress Plugin

This guide outlines a step-by-step process for managing your WordPress plugin to add/update in the WordPress repository using SVN (Subversion). SVN is a version control system that helps you track changes, collaborate with others, and maintain a history of your project.

## Step 1: Get the Plugin Files

Navigate to the directory where you want to store your plugin files locally and run the following command to fetch the initial copy from the SVN repository:

```bash
svn co https://plugins.svn.wordpress.org/your-plugin-name
```

Once WordPress approves your plugin they will provide you SVN URL. Replace `your-plugin-name` with the actual name of your WordPress plugin.

You should have got 3 directories:

- assets
- tags
- trunk

## Step 2: Make Changes

Make the necessary changes to your plugin files located in the `trunk` folder. This is where you'll work on your plugin's code, features, and bug fixes.

## Step 3: Add Changes to SVN

After making your changes, you need to add them to the SVN repository for version control. Use the following command to add all changes in the `trunk` folder:

```bash
svn add trunk/*
```

## Step 4: Update Existing Files

Before committing your changes, it's essential to ensure that your local copy is up to date with the latest changes from the SVN repository. Run the following command to update your local files:

```bash
svn up
```

## Step 5: Check for Changes

To see which files have been modified, added, or deleted in your local working copy, use the following command:

```bash
svn stat
```

## Step 6: Review Differences

To review the differences between your local copy and the SVN repository, you can use the following command:

```bash
svn diff
```

## Step 7: Create a Tag for a New Version

When you are ready to release a new version of your plugin, create a tag for that version using the following command:

```bash
svn cp trunk tags/1.0.0
```

Replace `1.0.0` with the actual version number of your plugin.

## Step 8: Commit Changes

Finally, commit your changes to the remote SVN repository with a meaningful commit message:

```bash
svn ci -m 'Adding the first version of my plugin' --username abc --password abc
```

Replace `abc` with your SVN username and password.

By following these steps, you can effectively manage the development and versioning of your WordPress plugin using SVN.

## Plugin Assets Icon/Banner/Screenshots

The assets folder in your plugin is where you can store images (like plugin headers, icons, and screenshots) used on your plugin’s display page.

### Banner Image

Image sizes should be the same as implied by the names. Supported file image file names & sizes are:

- Normal Banner: banner-772x250.(jpg|png)
- Normal Banner (Localized): banner-772x250-(rtl|es|es_ES).(jpg|png)
- High-DPI (Retina): banner-1544x500.(jpg|png)
- High-DPI (Retina Localized): banner-1544x500-(rtl|es|es_ES).(jpg|png)

### Icon Image

Supported file image file names & sizes are:

- Normal: icon-128x128.(png|jpg)
- High-DPI (Retina): icon-256x256.(png|jpg)
- SVG: icon.svg

### Screenshots

Screenshots show on the main page of your plugin and are used to illustrate aspects of the plugin admin dashboard or live examples. File name should be same as mentioned below:

- screenshot-1.(png|jpg)
- screenshot-2.(png|jpg)

**All filenames should be lowercase; uppercase names won’t work.**

**10MB is the maximum file size for screenshots, but as always, the smaller the better.**

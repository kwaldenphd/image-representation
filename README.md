# Image Representation
Image representation lab

The Laurel Leaf, WaterLilies, and Paradise images used in this lab were copied from [the original lab by Henry Walker](http://www.cs.grinnell.edu/~walker/courses/105.sp05/labs/image-processing.shtml). The rainbow image was created by Jerod Weinman and is released to the public domain.

## Acknowledgements
Created: 
- Henry Walker, January 30, 2004
Revised: 
- Henry Walker, February 16, 2005
- Marge Coahran, February 9, 2008
- Jerod Weinman, January 1, 2009
- Jerod Weinman, February 8, 2011
- Jerod Weinman, February 3, 2014
- Liz Rodrigues, February 9, 2019
- Katherine Walden, December 26, 2019

## Lab Overview + Objectives

In this lab, we'll compare file formats (GIF and JPEG), re-size image files, and explore the effects of image compression. As we covered in the encoding schema lab, computers store and process a variety of data types using a range of programs. In this lab, we'll be using the GNU Image Manipulation Program (GIMP) to work with image files on the command line.

# Installing GIMP

Open a Terminal window and use `sudo apt-get install gimp` to install GIMP on your Pi.

Once the installation is completed, you can launch GIMP's GUI interface under "Graphics" in your Start Menu.

#  Image Files

Download the four image files in this repo.

Using only the terminal, move the files into a newly-created folder for this lab.

Use the `ls -l` command to determine how many bytes are in each of the original image files.

<blockquote>Q1: How many bytes are in each of the original image files? How can you tell?</blockquote>

# JPEG Versus GIF Files

The encoding schema lab included an overview of RGB and hexadecimal color representation schema.

The JPEG file format can utilize the full range of RGB values. Although GIF files can include any particular color, they are limited to a maximum number (often 256) of colors total. 

GIF files are limited because they store colors in a table, and then refer to those colors by their position in the table (i.e., their index position), rather than by the full RGB triple.

Image processing software such as GIMP generally can work with images in two color modes: RGB mode, and indexed mode. JPEG images use RGB mode, and GIF images use indexed mode. 

To convert an image from the JPEG format to the GIF format (or back), you will need to change image modes.

# Changing Image Modes

Using the terminal, navigate to the newly-created directory with the image files.

`gimp college-logo.gif &` will open the `college-logo.gif` file in a window separate from your main terminal window.

The GIMP program will open several windows, including a picture with the image itself. At the top of the frame containing the picture, note that the caption includes the words `Indexed color` to show that a color table is being used.

To change the mode of the image to full RGB:
- Click on the Image menu
- Move your curser over the Mode sub-menu
- Click on RGB

The image frame caption should now read `RGB color` rather than `indexed color`.

To save the image as a `jpeg` file:
- Click the File menu and select Export
- In the Export Image dialog box, click on the triangle next to "Select File Type (By Extension)
- Select JPEG image for file type
- Check that the file name has changed to `college-logo.jpg`
- Click Export
- Accept the default quality (90) and click Save
** JPEG allows various quality settings. In general, the better the quality, the larger the file. 

Close the image window in GIMP. We do not need to save the file as a GIMP project.

Use `ls -l` to see the newly-created JPEG file.

<blockquote>Q2: How many bytes are there in <code>college-logo.gif</code>? How many bytes in <code>college-logo.jpg</code>?</blockquote>

https://digitalage19.sites.grinnell.edu/lab-4-image-representation/

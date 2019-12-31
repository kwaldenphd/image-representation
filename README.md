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

1. Open a Terminal window and use `sudo apt-get install gimp` to install GIMP on your Pi.

2. Once the installation is completed, you can launch GIMP's GUI interface under "Graphics" in your Start Menu.

#  Image Files

3. Download the four image files in this repo.

4. Using only the terminal, move the files into a newly-created folder for this lab.

5. Use the `ls -l` command to determine how many bytes are in each of the original image files.

<blockquote>Q1: How many bytes are in each of the original image files? How can you tell?</blockquote>

# JPEG Versus GIF Files

6. The encoding schema lab included an overview of RGB and hexadecimal color representation schema.

7. The JPEG file format can utilize the full range of RGB values. Although GIF files can include any particular color, they are limited to a maximum number (often 256) of colors total. 

8. GIF files are limited because they store colors in a table, and then refer to those colors by their position in the table (i.e., their index position), rather than by the full RGB triple.

9. Image processing software such as GIMP generally can work with images in two color modes: RGB mode, and indexed mode. JPEG images use RGB mode, and GIF images use indexed mode. 

10. To convert an image from the JPEG format to the GIF format (or back), you will need to change image modes.

# Changing Image Modes

11. Using the terminal, navigate to the newly-created directory with the image files.

12. `gimp college-logo.gif &` will open the `college-logo.gif` file in a window separate from your main terminal window.

13. The GIMP program will open several windows, including a picture with the image itself. At the top of the frame containing the picture, note that the caption includes the words `Indexed color` to show that a color table is being used.

14. To change the mode of the image to full RGB:
  a. Click on the Image menu
  b. Move your curser over the Mode sub-menu
  c. Click on RGB

15. The image frame caption should now read `RGB color` rather than `indexed color`.

16. To save the image as a `jpeg` file:
  a. Click the File menu and select Export
  b. In the Export Image dialog box, click on the triangle next to "Select File Type (By Extension)
  c. Select JPEG image for file type
  d. Check that the file name has changed to `college-logo.jpg`
  e. Click Export
  f. Accept the default quality (90) and click Save
    * JPEG allows various quality settings. In general, the better the quality, the larger the file. 

17. Close the image window in GIMP. We do not need to save the file as a GIMP project.

18. Use `ls -l` to see the newly-created JPEG file.

<blockquote>Q2: How many bytes are there in <code>college-logo.gif</code>? How many bytes in <code>college-logo.jpg</code>?</blockquote>

19. Open both of the `college-logo` image files by selecting Open from the File menu.

20. Arrange the two image windows so yu can see parts of both images as well as the GIMP toolbar.

21. Zoom in on a specific area of both `college-logo` images (at least 2000%). The magnifying glass icon on the GIMP toolbar will allow you to zoom in.

<blockquote>Q3: Describe what you see in each image, paying particular attention to colors. Which image format seems to be the most suitable for the logo image?</blockquote>

22. Close both image windows in GIMP. We do not need to save the file as a GIMP project.

# Creating GIF Files from JPEG Files

23. Converting an image from JPEG to GIF format with GIMP follows a similar process.

24. Open the `paradise.jpg` file in GIMP.

25. Change the color mode to `indexed`. 

26. Accepting the default number of colors (256) will cause a color table to be created for the image.

27. Save the image as as GIF file. Verify the file name is `paradise.gif` before clicking Export.

28. Close the `paradise.gif` image. We do not need to save the file as a GIMP project.

29. Open both of the `paradise` image files. 

30. Arrange the two image windows so yu can see parts of both images as well as the GIMP toolbar.

31. Zoom in on a specific area of both `paradise` images. Focus on the colors contained in a specific region of the image.

<blockquote>Q4: Use the terminal to check the size of each version of the <code>paradise</code> image. How many bytes does each one require?</blockquote>

<blockquote>Q5: What format seems most appropriate for the image?</blockquote>

<blockquote>Q6: Formulate a hypothesis about what times of images are most appropriate for each image format. What kinds of images work better as JPEG files? What kinds of images work better as GIF files?</blockquote>

32. Close both of the `paradise` images.

# Re-sizing Images

33. Using a new browser window, open the [Wikimedia Commons link](https://commons.wikimedia.org/wiki/File:Grinnell_College_Bucksbaum.jpg) to an image of Bucksbaum. Look at some of the different image resolutions. Note how long each image takes to load.

34. Full-size images posted on teh web can take a very long time to load based on the number of pixels being transferred to the user's computer. Resizing images is one way to help internet content load faster, especially for users in low-bandwidth or unreliable internet access.

35. Open the `water-lilies.jpg` file in GIMP.

36. Move your cursor to the bottom right-hand corner of the image, and look at the pixel coordinates displayed in the bottom left-hand side of the window.

<blockquote>Q7: Estimate the number of pixels in each row and column of this image.</blockquote>

37. Select Scale Image... from the Image menu. Change the width of the image to 600 pixels per row.

38. Press <Enter> or <Tab> to make sure the height of the image also changes to preserve the image's original "aspect ratio."
 
<blockquote>"The aspect ratio of an image describes the proportional relationship between its width and its height. It is commonly expressed as two numbers separated by a colon, as in 16:9. For an x:y aspect ratio, no matter how big or small the image is, if the width is divided into x units of equal length and the height is measured using this same length unit, the height will be measured to be y units." <a href="https://en.wikipedia.org/wiki/Aspect_ratio_(image)">(Wikipedia)</a></blockquote>

39. Click the Scale button to apply the size change. Use Save As to save a copy of the reduced-size image with a new file name.

<blockquote>Using Save instead of Save As will replace the original image with the reduced-size version.</blockquote>

<blockquote>Q8: We reduced the size of the image by 600/800 = 75%. What change do you expect to see in the file size?</blockquote>

<blockquote>Q9: How many bytes was the water-lilies file before you scaled it down? How many is it now? Does this match your prediction? If not, try to figure out why.</blockquote>

40. Close any open images.

# Exploring Image Compression

## Exploring GIF Compression

41. GIF uses a “lossless” compression method, in which the image file stored is smaller, but the resulting displayed image is the same. Let's explore how GIF represents images.

42. Open the `rainbow.gif` file in GIMP.

43. From the Image menu, select Transform and then Rotate 90&deg;. The image should now display vertical (rather than horizontal) stripes.

44. Save the rotated image with a new file name using the Export opion.

<blockquote>Q10: How many bytes is the original (horizontally striped) <code>rainbow.gif</code> file? How does this compare to the rotated (vertically striped) GIF file?</blockquote>

<blockquote>Q11: Why do you think the files are different sizes? Think about how you might describe this picture for someone else trying to draw it. What if you could only describe the color and horizontal image length?</blockquote>

## Exploring JPEG Compression

45. JPEG uses a “lossy” compression algorithm, which makes the image files much smaller, but they can be visibly affected because data is lost in the compression process. In this part you’ll explore these effects on image quality and file size.

46. Open the `water-lilies.jpg` file in GIMP.

47. Using the Export option, give the file a new name but keep the `jpg` extension. 

48. A dialog box titled `Save as JPEG` will appear. Check the `Show preview in image window` box.

49. Checking this box will allow you to see the compressed image without having to save and reopen it. Position the dialog box and the image window so you can see the image when changing the Quality slider.

50. Experiment with the Quality slider.

<blockquote>Q12: How quickly does the file size decrease? How much does the file size decrease before the difference in image quality becomes visibly noticeable?</blockquote>
  
<blockquote>Q13: How low can you set the Quality before the the image is drastically altered (e.g., blocky edges, strange colors and “noise”)? What is the file size? What does the image look like for extremely low Qualities (e.g. 1-6)?</blockquote>

<blockquote>Q14: Is it possible for certain images to be compressed (i.e. a quality less than 100) without visible loss? What can you conclude about the relationship between the compressed file size and visible image quality?</blockquote>

# Lab Notebook Questions

Q1: How many bytes are in each of the original image files? How can you tell?

Q2: How many bytes are there in <code>college-logo.gif</code>? How many bytes in <code>college-logo.jpg</code>?

Q3: Describe what you see in each image, paying particular attention to colors. Which image format seems to be the most suitable for the logo image?

Q4: Use the terminal to check the size of each version of the <code>paradise</code> image. How many bytes does each one require?

Q5: What format seems most appropriate for the image?

Q6: Formulate a hypothesis about what times of images are most appropriate for each image format. What kinds of images work better as JPEG files? What kinds of images work better as GIF files?

Q7: Estimate the number of pixels in each row and column of this image.

Q8: We reduced the size of the image by 600/800 = 75%. What change do you expect to see in the file size?

Q9: How many bytes was the water-lilies file before you scaled it down? How many is it now? Does this match your prediction? If not, try to figure out why.

Q10: How many bytes is the original (horizontally striped) <code>rainbow.gif</code> file? How does this compare to the rotated (vertically striped) GIF file?

Q11: Why do you think the files are different sizes? Think about how you might describe this picture for someone else trying to draw it. What if you could only describe the color and horizontal image length?

Q12: How quickly does the file size decrease? How much does the file size decrease before the difference in image quality becomes visibly noticeable?
  
Q13: How low can you set the Quality before the the image is drastically altered (e.g., blocky edges, strange colors and “noise”)? What is the file size? What does the image look like for extremely low Qualities (e.g. 1-6)?

Q14: Is it possible for certain images to be compressed (i.e. a quality less than 100) without visible loss? What can you conclude about the relationship between the compressed file size and visible image quality?

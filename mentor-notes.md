# Step by step mentors notes

## Table of Contents

[TOC]

---

## Step 1 - Create a new project with two pages

1. Click the 'New File' button in the top right hand corner of the screen.

![](https://i.imgur.com/eAb1V8Y.png)

2. We can rename our project by double clicking. Let's call it "book_borrowing_app".

3. Now let's create a new page and call it 'component-library'. Click the + icon next to 'Pages' in the Layers Panel

![](https://i.imgur.com/JzdNIbu.gif)

4. Rename 'Page 1' to 'prototype'

**TIP:** Don't create a Team for your project because Figma limits you to a single teammate when you do this on the free tier. Teams is a paid feature for large organisations working on multiple projects.

If we make a project without a team, we can invite as many people to collaborate as we like. :smile:

---

## Step 2 - Create a frame

A frame is a representation of a single screen from our web app.

In true mobile-first fashion, we're going to focus on making a prototype that we can test with mobile users.

**MENTOR NOTE:** We don't need to create separate prototypes for tablet or desktop - as we'll see later, there is a way to adapt this one for tablet and desktop devices.

1. Click on the 'Frame' tool in the Toolbar at the top of the screen.

![](https://i.imgur.com/MhAKt8t.png)

2. Now select the pre-defined iPhone 8 Frame size (375x667px) from the Properties Panel on the right.

![](https://i.imgur.com/fgiV1N7.png)

3. We're going to duplicate this frame by holding down the **Alt key** and clicking and dragging. Do this twice to create two more frames next to the first one.

![](https://i.imgur.com/PjCfjb2.png)

Double click the name of a frame to change it. We're going to call these three frames:

1. home-dev-books
2. home-design-books
3. home-other-books

**MENTOR NOTE:** It's good practice not to include whitespaces in Figma frame/object names because, when you export a project to SVG, the names are converted to ids (which can't contain spaces).

5. Making sure that our first frame is selected (click on the frame name to select it), click the 'Layout Grid' submenu in the Properties Panel to add a layout grid to the frame. To display columns, we need to click on the grid icon, then click on 'Grid' in the pop up menu, and select 'Columns' from the dropdown. Change the 'Count' to 6, the 'Margin' to 20, and the 'Gutter' to 10:

**MENTOR NOTE:** Margin is the space between columns, gutter is the space between the outermost columns and the side of the frame

![](https://i.imgur.com/UbWRw8V.png)

---

## Step 3 - Create component 1: Star rating

In this step, we create a set of star rating icons and we convert them into a reusable component.

1. Select the Star Tool from the main Toolbar

![](https://i.imgur.com/fARqBM2.png)

2. Draw a star measuring 16x16px in the home-dev-books frame. Change the **corner radius** to 0.2. Voila, we have a nicely-rounded 5-pointed star!
   ![](https://i.imgur.com/R6n9ccJ.png)
   > Setting the corner radius to 0.2 makes the points slightly rounded

![](https://i.imgur.com/FzDFshs.png)

**TIP:** Hold **Shift** while drawing to keep the width and height equal

**TIP:** Use **cmd +** to zoom in and **cmd -** to zoom out of the canvas

3. **Hold Alt + click** and drag the star to make four copies. Select them all (**Hold Shift + click**) and change the fill colour in the Properties Panel:

![](https://i.imgur.com/uFO6IdA.png)

4. With all the stars selected, right click the selection and hit 'Group Selection'. Name the group something sensible like 'star-rating'.

5. Copy the star-rating group over to our other frames. Center them horizontally and vertically.

![](https://i.imgur.com/5YFgiHV.png)

---

**Why do we need components?**

At this point, you can explain that the groups of objects we've just copied are independent from one another - when you change the styling on one, the others do not change. So, if we decide to change our app's colour palette, we'd have to apply the new colours to each group of stars individually.

**_Can the students think of why this could be a problem?_**

**_Hint: Imagine if, instead of 3 frames, our prototype had 30 frames, and that each one contained its own star-rating group? (it would take forever to update each one any time we change our design)_**

The solution is to create a **_master component_** that is connected to its **_child components_** (copies of the master component). Any changes that we make to the master component will automatically copy across to the child components.

---

**Turning the stars into a component**

Let's make our star ratings a little bit more component-like. Each star needs to be able to display 3 possible states: filled, half-filled, and unfilled

6. To make an unfilled star, copy the fifth filled star, change the colour to grey, then place it back on top of the fifth filled star. (Don't delete the fifth filled star - we need it)

![](https://i.imgur.com/iS9pV3v.gif)

**TIP:** You can toggle the visibility of any object by going to the Layers Panel (left side of the screen) and clicking on the eyeball icon next to an object.

![](https://i.imgur.com/lkSkH10.png)

7. We also need to make a half-greyed out star. Copy another filled in star, select the Rectangle Tool, and draw a rectangle across the right-hand side of the star. Making sure that both the rectangle and the star are selected, click the Boolean Groups dropdown menu in the Main Toolbar, and hit 'Subtract Selection'.

![](https://i.imgur.com/tI6RQpy.gif)

> Subtract Selection creates a subtraction group containing the full star and the rectangle. Only the non overlapping areas of both shapes are displayed, resulting in a half star effect.

> We've created a half star by subtracting the overlapping section

**TIP:** Subtract Selection is a _non-destructive command_, which means that the objects you use it on don't get destroyed or altered. It's a bit like adding an Instagram filter to a photo.

8. Move the half star on top of the fifth star. Positioning the half star exactly on top can be fiddly - to get pixel perfect placement, you have to make sure you select both elements inside the subtraction group (**hold Shift + click** to select multiple ones) before placing it.

![](https://i.imgur.com/UdNE5tu.gif)

9. Rename the stars so you know which layer is which. Reorder them if needed - make sure that star-half-filled is at the front, star-filled in the middle, and star-unfilled at the back

![](https://i.imgur.com/OLlDz00.gif)

10. Select all three star layers and group them (**cmd + G**, or right click and 'Group Selection')

![](https://i.imgur.com/OCydlNQ.gif)

11. Copy the group four times (**hold option + click & drag**)

![](https://i.imgur.com/S4FQNgT.gif)

12. Select all five stars go to the Main Toolbar, and click the 'Create Component' button.

![](https://i.imgur.com/os4gLHT.gif)

Congratulations! We've created a component! :yellow_heart:

13. Now let’s copy the star-rating component to make three child components

![](https://i.imgur.com/jFm66lc.gif)

14. We'll move the master component over to the component-library page of our project

![](https://i.imgur.com/w6nLC9S.gif)

**TIP:** It’s good practice to keep master components separate from our prototype and just to use child components to flesh out our frames - this makes it easy to control everything from a small number of master components, in one place.

---

## Step 4 - Create component 2: Menu bar w/ Plugins

In 2019, Figma added support for Plugins - third party add-ons that extend its functionality in a bunch of different ways.

In this step, we're going to use a plugin called Iconify to import pre-made UI icons for the main menu bar component of our app.

1. In the Toolbar, click on the hamburger menu icon > Plugins > Manage plugins

2. Click Browse all plugins, locate Iconify, click Install. Go back to the project and check that Iconify appears in the Plugins dropdown from the Toolbar

![](https://i.imgur.com/lBvbfPk.gif)

![](https://i.imgur.com/ksgfwBV.png)

3. Bring up the Iconify menu and search for a menu icon in the search field. Drag and drop your favourite icon into a frame

![](https://i.imgur.com/cYoxLKv.gif)

4. Resize the icon (24x24px works for our app), align it with the edge of the left gutter, and change its colour.

![](https://i.imgur.com/HfoUn67.png)

5. Now do the same to find a search icon and place it in the top right corner of our frame

![](https://i.imgur.com/mlz8qRk.png)

6. To create the page title, select the Text Tool (shortcut: **K key**), draw a text box, type 'Popular Books' inside it, and style it as needed

![](https://i.imgur.com/ycERBgi.gif)

7. Turn these three objects into a component. We'll call it 'main-nav'

![](https://i.imgur.com/EfQCP86.gif)

---

## Step 5 - Create component 3: Image carousel

1. Draw three rectangles with the following dimensions:

- 220x220px (for the image on the left)
- 200x200px (for the middle image)
- 200x200px (for the image on the right)

Position them so that the largest rectangle is in the middle. Make sure that they are all contained inside the selected frame.

2. Select the frame and check the 'Clip content' checkbox in the Properties Panel to remove the overflowing areas from view

![](https://i.imgur.com/OLpMu04.gif)

3. Now let's add an image. To do this, select the middle rectangle. Go in the Properties Panel to the Fill section and click the plus icon to add a new fill. Change the fill type from 'Linear' to 'Image'

![](https://i.imgur.com/p0LPF4w.gif)

4. Click 'Choose image' and select one of the book cover JPEGs that are saved in this repo (in the book-covers folder)

5. To resize the image to fit the rectangle, change the image size from 'Fill' to 'Fit'

![](https://i.imgur.com/yU4Pr7P.gif)

6. Now repeat steps 2-5 to add the relevant book covers to the other rectangles in our carousel. Stack three book covers on top of one another as before. You should end up with something that looks like this:

![](https://i.imgur.com/8UYQpE1.png)

7. We need to create the carousel section controls too. Using the Text tool, draw three text boxes and give them the text 'DESIGN', 'DEVELOPMENT', and 'OTHER'

![](https://i.imgur.com/n7qh7FW.png)

8. To underline each text box using the Line tool

9. Convert everything we just made into a component called 'carousel'

![](https://i.imgur.com/VgblpqH.gif)

10. When we copy this component into our other frames, we can show/hide the different images to show books from the different categories. We can also apply opacity to the inactive book category names.

![](https://i.imgur.com/f9WmP7Y.png)

**TIP:** Remember to put the master carousel component in our component-library!

## Step 6 - Link up screens in prototype mode

1. Click onto the 'Prototype' tab in the Properties Panel

![](https://i.imgur.com/YHhkn1n.png)

2. Select the element that you want users to be able to tap/click, then click and drag the white circle on the right side over to the frame that you want it to take users to. You should see a blue arrow connecting them

![](https://i.imgur.com/dU3wEmw.gif)

3. Link up the other frames in the same way

![](https://i.imgur.com/nJHGMWy.png)

4. Press the blue Share button in the top right corner of the screen to enter the interactive prototype mode. Show the students how it switches from frame to frame when you click on the book category names

![](https://i.imgur.com/STTGnNX.gif)

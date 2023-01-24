
# Tableau: Filters, colors, and more tips and tricks
If you've completed our first Tableau exercise, or if you already know how to do basic stuff in Tableau, this tutorial will show you how to do a few more interesting things. You'll switch among visualization types, learn how filters work, expose controls to the user, and test your skills on a couple of challenges.

# Table of contents
1 Welcome (or welcome back)!
2 Import your dataset
3 Correct your data types
4 Get oriented with our data
5 Add a measure to our chart
6 Our first visualization
7 From horizontal to vertical
8 Filter your dates
9 Add another dimension to your chart
10 View the data as a highlight table
11 See the top 10 years
12 Change the X axis
13 Try this
14 Try this
15 Change the look of your chart
16 Give the users control

## 1 Welcome (or welcome back)!
So you have some experience with Tableau—enough to navigate the user interface and make some basic charts. Let's look at a few of the tool's more advanced features.

For this tutorial, please download [this dataset](https://www.dropbox.com/s/p3xpsd7ubpmg6m5/accused_witches.csv?dl=1). (It comes from the [Survey of Scottish Witchcraft Database](http://witches.shca.ed.ac.uk/)!)

## 2 Import your dataset
![Import your dataset](steps-tableau__filters__colors__and_more_tips_and_tricks/step-1.jpeg)
Start a new Tableau worksheet (**File** -> **New Worksheet**) and import the witchcraft file as you did in the previous tutorial. Remember, a .csv file is a text file.

## 3 Correct your data types
![Correct your data types](steps-tableau__filters__colors__and_more_tips_and_tricks/step-2.jpeg)
Once you've imported the dataset, click on **Sheet** (the orange button at the bottom left of the Tableau window) to be taken to the visualization workspace.

Let's take a look at the fields available to us in Tableau's **Data** pane. As before, we have both measures and dimensions. 

Tableau tries to guess what kind of data is in each of your columns, and it does a pretty good job. But I do notice a mistake: it's imported **Date** as a string (a set of characters), not a calendar date. You can tell because the little blue icon to the left of the word "Date" is a tiny "Abc" instead a calendar. 

Let's change that. Click on the word **Date** to reveal a dropdown menu. From the menu, choose **Change Data Type**, and then **Date**. The icon next to **Date **should now look like a little calendar.

(You could also click on the "Abc" icon directly to accomplish the same thing.)

## 4 Get oriented with our data
![Get oriented with our data](steps-tableau__filters__colors__and_more_tips_and_tricks/step-3.jpeg)
Let's try to figure out the general contours of our data. My first inclination is to figure out how many people were accused of witchcraft over time.

We want to see a distribution over time, so we know we'll want our chart to include the date. Grab the **Date** field and drop it on the left side of your canvas.

Now you have a list of dates. And if you look above the canvas, you'll see that a "pill" containing YEAR(Date) has appeared on the **Rows** shelf.

## 5 Add a measure to our chart
![Add a measure to our chart](steps-tableau__filters__colors__and_more_tips_and_tricks/step-4.jpeg)
We now have a list of dates, but Tableau still doesn't know what you want it to *show* you for those dates.

We want to know the sum of all people accused of witchcraft during those years. Which of our measures could show us that?

We want to use the generated count again: that is, the count of records that Tableau has added to our list of measures. It looks like this: *accused_witches (2).csv (Count)*. Grab that measure and drop it in our table, in the column that's currently populated by rows reading "Abc."

Now, the second column in your table should give you a count of all the records for that year.

## 6 Our first visualization
![Our first visualization](steps-tableau__filters__colors__and_more_tips_and_tricks/step-5.jpeg)
It's nice to start out with a simple chart, so click on the **horizontal ba**r tile in the **Show me** pane.

That sort of works, in the sense that a bar chart appears, but it's a bit hard to read. Two things bug me: first, it would be easier to understand if the dates appeared on the horizontal axis, and second, there are so many "null" values that they distort the scale of the graph, so that every other year looks similar in comparison.

## 7 From horizontal to vertical
![From horizontal to vertical](steps-tableau__filters__colors__and_more_tips_and_tricks/step-6.jpeg)
Let's start by switching the axes of our bar chart, so that the date appears along the bottom.

Luckily, there's a button for that! Find it in Tableau's top toolbar: a series of squares with an arrow indicating a switch.

When you click the button, you'll see that the blue and green pills switch places on the row and column shelves, and your axes reconfigure themselves so that the date runs along the bottom.

Better! But let's get rid of those null values.

## 8 Filter your dates
![Filter your dates](steps-tableau__filters__colors__and_more_tips_and_tricks/step-7.jpeg)
To filter out the null values, click on the dropdown arrow on the blue "pill" that reads YEAR(Date) in the** Columns** shelf. From the menu that emerges, click **Filter**. 

Now we can see our options for filtering out year values. This is pretty straightforward! Uncheck the **Null** checkbox, then click **OK**. 

Now it's a bit easier to see which years saw the most witchcraft accusations.

## 9 Add another dimension to your chart
![Add another dimension to your chart](steps-tableau__filters__colors__and_more_tips_and_tricks/step-8.jpeg)
It would be nice to see the sex breakdowns of accusations per year. To do that, grab the **Sex **field from the left-hand list and drop on the **Color** tile on the **Marks** pane. (You could also drop it directly on the canvas; you can often do things multiple ways in Tableau.)

Perhaps you'd like to change the default colors on the stacked bar chart that you now see. To do that, you'll want to reveal your **Legend**—right now it's probably covered by the **Show me** pane (the pallet of visualization types at the top right of your window).

To reveal the legend, click on the words **Show me** at the top of the "Show me" pane in order to collapse that menu. You should now see a legend. Double-click on any of the elements to change their assigned colors. (You can bring back the Show me pane by clicking again on its name.)

## 10 View the data as a highlight table
![View the data as a highlight table](steps-tableau__filters__colors__and_more_tips_and_tricks/step-9.jpeg)
The bar chart is helpful, but let's try another visualization type for comparison. From the **Show me** pane, select the **highlight table**: it's a grid of green and yellow rectangles.

It's probably easier to see the table if the years run vertically, so use the **Swap rows and columns** button again to change the orientation.

Compare this chart to the bar chart. Does your eye more easily spot the very active years? What are the relative strengths of each type of chart?

(You might like to play with the chart's details, too. If you look at the dropdown menu immediately beneath the title of the **Marks** pane, you'll see that **Square **is selected. What happens if you switch that to **Circle**? What happens if you drag *accused_witches(2).csv (Count)* on to the **Size** button on the **Marks** pane?)

## 11 See the top 10 years
![See the top 10 years](steps-tableau__filters__colors__and_more_tips_and_tricks/step-10.jpeg)
Go back to the stacked bar chart view of your data.

Perhaps it would be useful to see which years saw the most accusations of witchcraft. To do this, we'll use a different kind of filter.

From the blue **YEAR(Date)** pill on the **Columns** shelf, click the dropdown arrow and then select **Filter.** This time, click on the **Top** button. Click the **By field** radio button and set the parameters to Top 10 by Count (as shown). Then click **OK**.

Try filtering by other parameters, too. Can you figure out how to show only those years in which at least 10 people were accused of witchcraft? (You'll need to use the **Condition** pane.)

How can we show the data for only female accused witches? (You'll need to set another filter, this time on **Sex**.)

## 12 Change the X axis
![Change the X axis](steps-tableau__filters__colors__and_more_tips_and_tricks/step-11.jpeg)
So far, we've been viewing our data by date. Let's try changing that to county, to see if we notice anything else that strikes our attention. 

Drag the **Res county** field to the **Columns** shelf. Remove the **YEAR(Date)** pill by clicking its down arrow and selecting **Remove**. 

Now we see the activity by county in the 10 years during which there were the most witchcraft accusations (because, remember, our YEAR(Date) filter is still active; you can remove it if you want).

If you'd like, you can sort the counties in ascending or descending order, using the buttons immediately to the right of the Switch Columns and Rows button.

## 13 Try this
![Try this](steps-tableau__filters__colors__and_more_tips_and_tricks/step-12.jpeg)
Can you create a chart that displays the sex breakdown of the top 10 occupations of the accused? (See the video for a solution.)

## 14 Try this
![Try this](steps-tableau__filters__colors__and_more_tips_and_tricks/step-13.jpeg)
Can you create [sparklines](https://en.wikipedia.org/wiki/Sparkline) showing accusations in the top 10 counties for witchcraft accusations? (You can hide the titles for the axes by right-clicking on them and then unchecking **Show header**.)

(See the video for a solution.)

## 15 Change the look of your chart
![Change the look of your chart](steps-tableau__filters__colors__and_more_tips_and_tricks/step-14.jpeg)
You can customize the look of just about anything on your chart! Right-click (or control-click) on your canvas and select **Format** from the dropdown menu. You'll see that you can switch up your fonts, their layout, color and shading, borders, and many other attributes. 

Remember, to change the attributes of the "marks" (the actual data) on your chart, you'll work with the **Marks** pane or the **Legend**.

## 16 Give the users control
![Give the users control](steps-tableau__filters__colors__and_more_tips_and_tricks/step-15.jpeg)
Once you're happy with your final product, let's make it possible for the users to apply filters themselves.

For the **YEAR(Date) **filter, first change the data type from **Discrete** to **Continuous**. This allows the years to be shown as a flowing range of values, rather than individual checkboxes.

Then, select **Show Filter** from the dropdown menu. You'll be able to see a date scrubber next to your chart.

Now, when you publish your chart, your user will be able to change the date range.

From bar charts to filters to user controls, you know how to do a lot with Tableau! If you have some time, [learn about making animations](https://www.tableau.com/blog/bring-your-data-life-viz-animations).



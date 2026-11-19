# Facets in OpenRefine

Facets are a useful (and powerful!) tool within OpenRefine for getting a big picture understanding of your data. Facetting groups all like values in a column together, and allows you to filter and edit those values en masse. Facets can also help you visualize your data. 

OpenRefine includes several options for facets, specifically: 

- Text facets
- Numerical facets
- Timeline/date facets
- Scatterplot facets 
- Custom

You can access the facetting options by clicking on the down arrow beside a variable title and then hovering over the `Facet` heading. 

## Text facets

First, let's try a text facet on the movie genre variable. A text facet groups all the identical text values in a column and creates a list in a box in the left margin with the unique text values and the number of times each value appears in the faceted column. 

Click the down arrow button beside the **primary_genre** title and hover over `Facet`, then click on `Text Facet`. 

<figure markdown="span">
    ![image showing the facet menu](./content/facet_menu.jpg){width=800}
    <figcaption></figcaption>
</figure>
 
 A text facet should appear as a box, labelled with the variable being facetted, on the left hand side of your window. Your **primary_genre** facet should have 28 choices. These can be sorted either alphabetically by name, or by count in descending order. Scroll through the list of primary genres - do you notice any errors or issues? 

<figure markdown="span">
    ![image of the facet menu for primary genre](./content/text_facet.png){width=800}
    <figcaption></figcaption>
</figure>

You should see a number of mistyped or incorrectly labelled genre titles. Let's fix one of these.

Hover over the **Documntary** line and click on **edit** when the option appears. This will open a small text window that we can use to correct the mispelling. Correct the genre title and click `Apply`. Notice that the film that was incorrectly labelled has now been absorbed into the correctly spelled **Documentary** genre. 

Leave the other errors, we'll use other OpenRefine techniques to correct them. 

## Other facets and custom facets

Timeline facets work much the same way as text facets: unique values are grouped together, and then listed along with the number of times that they appear in the column. 

Numeric and scatterplot facets, on the other hand, display graphs instead of lists. Scatterplots, moreover, allow you to visualise the values of a pair of numeric columns, and to filter data by two-value combinations. 

Let's try creating a numeric facet to get a sense of the range of average ratings of the movies in our dataset. Start by pressing the down arrow button beside **ave_rating** and the hover other `Facet`. Select `Numeric facet` from the option. What happened?

???note "If something went wrong..."
    A facet labelled **ave_rating** should have appeared in the left pane in your window; however, it will not have a graph in it. Instead, it will have a message saying 'No numeric value present.' This is happening because our rating data is not correctly identified as numeric data. 

We can use transformations in OpenRefine to edit our data types. Go back to the same dropdown menu on the ratings column, but this time hover over `Edit cells` and then to `Common transforms`. From there, select `To number`. 

<figure markdown="span">
    ![image showing the facet menu](./content/ave_rating_transform.png){width=800}
    <figcaption></figcaption>
</figure>

The values in the **ave_rating** column should now have changed colour (to green) and alignment within the column (right-aligned). The facet for average rating should also have automatically updated to show a histogram of the average movie rating. 

<figure markdown="span">
    ![image showing the facet menu](./content/ave_rating_facet.png){width=800}
    <figcaption></figcaption>
</figure>

Go ahead and edit data in the **num_votes** and **runtime** columns to be numeric as well.

Let's also use a transformation to correct the data type of the movie years in the **year** column. 

???note "Solution"
    Navigate to the dropdown menu for the **year** variable, and follow this path:

    `Edit cells` --> `Common transforms` --> `To date`

Beyond the four primary facet options (text, numeric, timeline, and scatterplot) OpenRefine also includes a number of customized facets, and allows you to write your own custom text and numeric facets. 

One such useful customized facet is the facet by error. This will group your data by whether or not there are errors. Let's try making a facet by error for **runtime**. 

On my end, a facet appears in the left side pane, but with only one item ("false") and a count of 4884. This means that there are no errors in any of the 4884 rows in my dataset.

You can close a facet by clicking the `x` in the top right corner of the facet. 

Faceting is just one way to identify and correct errors. OpenRefine also allows us to use transformations and clustering, sometimes in conjunction with facets, to do that. 




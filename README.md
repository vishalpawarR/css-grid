# css-grid

Introduction to the CSS Grid Challenges

- CSS Grid helps you easily build complex web designs. It works by turning an HTML element into a grid container with rows and columns for you to place children elements where you want within the grid.

## 1 - Create Your First CSS Grid :

- Turn any HTML element into a grid container by setting its `display` property to `grid`. This gives you the ability to use all the other properties associated with CSS Grid.

Note: In CSS Grid, the parent element is referred to as the container and its children are called items.

Change the display of the div with the `container` class to `grid`.

## 2 - Add Columns with grid-template-columns :

- Simply creating a grid element doesn't get you very far. You need to define the structure of the grid as well. To add some columns to the grid, use the `grid-template-columns` property on a grid container as demonstrated below:

```css
.container {
  display: grid;
  grid-template-columns: 50px 50px;
}
```

- This will give your grid two columns that are each 50px wide. The number of parameters given to the `grid-template-columns` property indicates the number of columns in the grid, and the value of each parameter indicates the width of each column.

Give the grid container three columns that are each `100px` wide.

## 3 - Add Rows with grid-template-rows :

- The grid you created in the last challenge will set the number of rows automatically. To adjust the rows manually, use the `grid-template-rows` property in the same way you used `grid-template-columns` in previous challenge.

Add two rows to the grid that are `50px` tall each.

## 4 - Use CSS Grid units to Change the Size of Columns and Rows :

- You can use absolute and relative units like px and em in CSS Grid to define the size of rows and columns. You can use these as well:

- `fr`: sets the column or row to a fraction of the available space,

- `auto`: sets the column or row to the width or height of its content automatically,

- `%`: adjusts the column or row to the percent width of its container.

Here's the code that generates the output in the preview:

```css
grid-template-columns: auto 50px 10% 2fr 1fr;
```

- This snippet creates five columns. The first column is as wide as its content, the second column is 50px, the third column is 10% of its container, and for the last two columns; the remaining space is divided into three sections, two are allocated for the fourth column, and one for the fifth.

- Make a grid with three columns whose widths are as follows: 1fr, 100px, and 2fr.

## 5 - Create a Column Gap Using grid-column-gap :

- So far in the grids you have created, the columns have all been tight up against each other. Sometimes you want a gap in between the columns. To add a gap between the columns, use the `grid-column-gap` property like this:

```css
grid-column-gap: 10px;
```

- This creates 10px of empty space between all of our columns.

- Give the columns in the grid a `20px` gap.

## 6 - Create a Row Gap using grid-row-gap :

- You can add a gap in between the rows of a grid using `grid-row-gap` in the same way that you added a gap in between columns in the previous challenge.

Create a gap for the rows that is `5px` tall.

## 7 - Add Gaps Faster with grid-gap :

- `grid-gap` is a shorthand property for `grid-row-gap` and `grid-column-gap` from the previous two challenges that's more convenient to use. If `grid-gap` has one value, it will create a gap between all rows and columns. However, if there are two values, it will use the first one to set the gap between the rows and the second value for the columns.

- Use `grid-gap` to introduce a `10px` gap between the rows and `20px` gap between the columns.

## 8 - Use grid-column to Control Spacing :

- Up to this point, all the properties that have been discussed are for grid containers. The `grid-column` property is the first one for use on the grid items themselves.

- The hypothetical horizontal and vertical lines that create the grid are referred to as lines. These lines are numbered starting with 1 at the top left corner of the grid and move right for columns and down for rows, counting upward.

- This is what the lines look like for a 3x3 grid:
  ![Grid column](grid-column.PNG)
- column lines1234row lines1234
  To control the amount of columns an item will consume, you can use the `grid-column` property in conjunction with the line numbers you want the item to start and stop at.

Here's an example:

```css
grid-column: 1 / 3;
```

- This will make the item start at the first vertical line of the grid on the left and span to the 3rd line of the grid, consuming two columns.

- Make the item with the class `item5` consume the last two columns of the grid.

## 9 - Use grid-row to Control Spacing :

- Of course, you can make items consume multiple rows just like you can with columns. You define the horizontal lines you want an item to start and stop at using the grid-row property on a grid item.

- Make the element with the item5 class consume the last two rows.

## 10 - Align an Item Horizontally using justify-self :

- In CSS Grid, the content of each item is located in a box which is referred to as a cell. You can align the content's position within its cell horizontally using the `justify-self` property on a grid item. By default, this property has a value of `stretch`, which will make the content fill the whole width of the cell. This CSS Grid property accepts other values as well:

- `start`: aligns the content at the left of the cell,

- `center`: aligns the content in the center of the cell,

- `end`: aligns the content at the right of the cell.

- Use the `justify-self` property to center the item with the class `item2`.

## 11 - Align an Item Vertically using align-self :

- Just as you can align an item horizontally, there's a way to align an item vertically as well. To do this, you use the `align-self` property on an item. This property accepts all of the same values as `justify-self` from the last challenge.

- Align the item with the class `item3` vertically at the `end`.

## 12 - Align All Items Horizontally using justify-items :

- Sometimes you want all the items in your CSS Grid to share the same alignment. You can use the previously learned properties and align them individually, or you can align them all at once horizontally by using `justify-items` on your grid container. This property can accept all the same values you learned about in the previous two challenges, the difference being that it will move all the items in our grid to the desired alignment.

- Use this property to center all our items horizontally.

## 13 - Align All Items Vertically using align-items :

- Using the `align-items` property on a grid container will set the vertical alignment for all the items in our grid.

- Use it now to move all the items to the end of each cell.

## 14 - Divide the Grid Into an Area Template :

- You can group cells of your grid together into an area and give the area a custom name. Do this by using `grid-template-areas` on the container like this:

```css
grid-template-areas:
  "header header header"
  "advert content content"
  "footer footer footer";
```

- The code above merges the top three cells together into an area named `header`, the bottom three cells into a `footer` area, and it makes two areas in the middle row; `advert` and `content`. Note: Every word in the code represents a cell and every pair of quotation marks represent a row. In addition to custom labels, you can use a period (`.`) to designate an empty cell in the grid.

Place the area template so that the cell labeled `advert` becomes an empty cell.

## 15 - Place Items in Grid Areas Using the grid-area Property :

- After creating an area's template for your grid container, as shown in the previous challenge, you can place an item in your custom area by referencing the name you gave it. To do this, you use the `grid-area` property on an item like this:

```css
.item1 {
  grid-area: header;
}
```

- This lets the grid know that you want the `item1` class to go in the area named `header`. In this case, the item will use the entire top row because that whole row is named as the header area.

- Place an element with the `item5` class in the `footer` area using the `grid-area` property.

## 16 - Use grid-area Without Creating an Areas Template :

- The `grid-area` property you learned in the last challenge can be used in another way. If your grid doesn't have an areas template to reference, you can create an area on the fly for an item to be placed like this:

```css
item1 {
  grid-area: 1/1/2/4;
}
```

- This is using the line numbers you learned about earlier to define where the area for this item will be. The numbers in the example above represent these values:

```css
grid-area: horizontal line to start at / vertical line to start at / horizontal
  line to end at / vertical line to end at;
```

- So the item in the example will consume the rows between lines 1 and 2, and the columns between lines 1 and 4.

- Using the `grid-area` property, place the element with `item5` class between the third and fourth horizontal lines and between the first and fourth vertical lines.

## 17 - Reduce Repetition Using the repeat Function :

- When you used `grid-template-columns` and `grid-template-rows` to define the structure of a grid, you entered a value for each row or column you created.

- Let's say you want a grid with 100 rows of the same height. It isn't very practical to insert 100 values individually. Fortunately, there's a better way - by using the `repeat` function to specify the number of times you want your column or row to be repeated, followed by a comma and the value you want to repeat.

- Here's an example that would create the 100 row grid, each row at 50px tall.

```css
grid-template-rows: repeat(100, 50px);
```

- You can also repeat multiple values with the repeat function and insert the function amongst other values when defining a grid structure. Here's what that looks like:

```css
grid-template-columns: repeat(2, 1fr 50px) 20px;
```

This translates to:

```css
grid-template-columns: 1fr 50px 1fr 50px 20px;
```

> Note: The `1fr 50px` is repeated twice followed by 20px.

- Use `repeat` to remove repetition from the `grid-template-columns` property.

## 18 - Limit Item Size Using the minmax Function :

- There's another built-in function to use with `grid-template-columns` and `grid-template-rows` called minmax. It's used to limit the size of items when the grid container changes size. To do this you need to specify the acceptable size range for your item. Here is an example:

```css
grid-template-columns: 100px minmax(50px, 200px);
```

- In the code above, `grid-template-columns` is set to create two columns; the first is 100px wide, and the second has the minimum width of 50px and the maximum width of 200px.

Using the `minmax` function, replace the `1fr` in the `repeat` function with a column size that has the minimum width of `90px` and the maximum width of `1fr`, and resize the preview panel to see the effect.

## 19 - Create Flexible Layouts Using auto-fill :

- The repeat function comes with an option called auto-fill. This allows you to automatically insert as many rows or columns of your desired size as possible depending on the size of the container. You can create flexible layouts when combining `auto-fill` with `minmax`, like this:

```css
repeat(auto-fill, minmax(60px, 1fr));
```

- When the container changes size, this setup keeps inserting 60px columns and stretching them until it can insert another one. Note: If your container can't fit all your items on one row, it will move them down to a new one.

- In the first grid, use `auto-fill` with `repeat` to fill the grid with columns that have a minimum width of `60px` and maximum of `1fr`. Then resize the preview to see auto-fill in action.

## 20 - Create Flexible Layouts Using auto-fit :

- `auto-fit` works almost identically to `auto-fill`. The only difference is that when the container's size exceeds the size of all the items combined, `auto-fill` keeps inserting empty rows or columns and pushes your items to the side, while `auto-fit` collapses those empty rows or columns and stretches your items to fit the size of the container.

> Note: If your container can't fit all your items on one row, it will move them down to a new one.

- In the second grid, use `auto-fit` with `repeat` to fill the grid with columns that have a minimum width of `60px` and maximum of `1fr`. Then resize the preview to see the difference.

## 21 - Use Media Queries to Create Responsive Layouts :

- CSS Grid can be an easy way to make your site more responsive by using media queries to rearrange grid areas, change dimensions of a grid, and rearrange the placement of items.

- In the preview, when the viewport width is 300px or more, the number of columns changes from 1 to 2. The advertisement area then occupies the left column completely.

- When the viewport width is `400px` or more, make the header area occupy the top row completely and the footer area occupy the bottom row completely.

LAYOUT THE STREAMLIT


![LAYOUT THE STREAMLIT](https://github.com/ywangnccu/ywang/blob/main/images/STREAMLIT/STREAMLIT.png)

Streamlit is a faster way to build and share data apps. 
It is the open-source Python framework.
Streamlit is awesome we several cool and useful features, 
in this tutorial we will explore yet another additional feature of streamlit – st.beta_columns() and st.beta_expander().

This feature is available from version 0.68 and upwards hence you will need to upgrade your previous version via

pip install streamit -U 
or

pip install streamlit --upgrade
Let us understand the basic overview of the layout in streamlit.

In previous versions of streamlit you could only use either the extensive mode or some hacks with the html to layout your app. 
However, with the recent updated version from 0.68 you can layout your app with your widget side by side in a format of a grid.

Very cool

To layout your app you will need the st.beta_columns() function. 
This allows you to create side by side grid-like columns that offers every widget and extra feature of streamlit.

It is like having another streamlit within your streamlit app as it inherit most if not every various method and attribute of the DeltaGenerator class that st.sidebar belongs to.

Let us see how to lay out our app

Defining the Number of Columns
For creating any number of side by side columns you can specify the number of columns or containers you want and it will automatically partition the entire section into the respective halves or sections.

So to create 2 side by side columns you can do

col1,col2 = st.beta_columns(2)
For creating side by side columns with one being of a different width you can also do so by parsing into the function a list of integers according to how you want the partition to be

col1,col2 = st.beta_columns([3,1])
So [3,1] means I want two columns but let the first be 3 times and the last column to be of only One of the previous. 
It will automatically partition the entire layout for you. Cool right! Below is a picture to show the process


![LAYOUT THE STREAMLIT](https://github.com/ywangnccu/ywang/blob/main/images/STREAMLIT/STREAMLIT1.png)

Placing Your Code/Widget in the Columns
Now after defining the columns you can place your functions, the widget,etc in the respective column by using two methods.

Method 1 - As blocks

In this case you can call the widget as a method or an attribute with the variable name you unpacked that column to. So for example

col1,col2 = st.beta_columns(2) 
col1.success("First Column")
col1.button("Hello")
col2.success("Second COlumn")
col2.button("Hello From Col2")
Like that

![LAYOUT THE STREAMLIT](https://github.com/ywangnccu/ywang/blob/main/images/STREAMLIT/STREAMLIT3.png)

Similarly if you want to specify different width you can also use the same format


![LAYOUT THE STREAMLIT](https://github.com/ywangnccu/ywang/blob/main/images/STREAMLIT/STREAMLIT5.png)

Method 2 - Using Context Manager

With this method you use the ‘with’ keyword just like any context manager in python and place your code,widget and cool things under.

col1,col2 = st.beta_columns(2)

with col1:
    st.success("From Col1")
    mytext = st.text_area("Enter Text Here")

with col2:
   st.info("From Col2")
   my_year = st.number_input("Year",1995,2040)
   st.write(my_year)
   

![LAYOUT THE STREAMLIT](https://github.com/ywangnccu/ywang/blob/main/images/STREAMLIT/STREAMLIT6.png)

Awesome right. That is how to add layout to your streamlit app using the st.beta_columns() . Let us know what you do with it.

(I appreciate JCharisTech for sharing the above knowledge. Please let me know if it is against the copyright.)

Landing Page Template with React JS and Material UI 🎯
Site: HBSales







Table of Contents
About
Learnings
Dependencies
About
This is a landing page template created with React JS, designed for developers and designers who want to quickly build a professional landing page for their open-source projects.

Learnings
:heavy_check_mark: React Router v6+ in the DOM

In App.js:

jsx
Copy code
import { BrowserRouter, Routes, Route } from 'react-router-dom';
The Navbar component has elements that repeat across all pages and components that are within 'Routes', so it is placed inside 'BrowserRouter'.

jsx
Copy code
<BrowserRouter>
    <Navbar />
    <Routes>
        <Route path='/' element={<Home />} />
        <Route path='/about' element={<About />} />
        <Route path='/contact' element={<Contact />} />
    </Routes>
</BrowserRouter>
Inside the pages folder in Home.js:

jsx
Copy code
const Home = () => {
  return (
    <>
      <Header />
      <GetStarted />
      <GetInTouch />
    </>
  );
};
Inside the Navbar component:

jsx
Copy code
import { Link } from 'react-router-dom';
import { AppBar, List, ListItem, ListItemButton, ListItemText, Typography } from '@mui/material';
import { styled } from '@mui/material/styles';

const itemList = [
    { text: "Home", to: "/" },
    { text: "About", to: "/about" },
    { text: "Contact", to: "/contact" }
];

const Navbar = () => {
    return (
        <AppBar 
            component="nav" 
            position="sticky"
            sx={{ backgroundColor: 'orange' }}
            elevation={0}
        >
            <StyledToolbar>
                <Typography variant="h6" component="h2">
                    HBSales
                </Typography>
                <ListMenu>
                    {itemList.map((item) => {
                        const { text, to } = item;
                        return (
                            <ListItem key={text}>
                                <ListItemButton component={Link} to={to}
                                    sx={{
                                        color: '#fff',
                                        "&:hover": {
                                            backgroundColor: 'transparent',
                                            color: '#1e2a5a',
                                        }
                                    }}
                                >
                                    <ListItemText primary={text} />
                                </ListItemButton>
                            </ListItem>
                        );
                    })}
                </ListMenu>
            </StyledToolbar>
        </AppBar>
    );
};

export default Navbar;
:heavy_check_mark: Using sx and Breakpoints in Material UI

What is sx?

The sx prop allows you to work with a superset of CSS that wraps all the style functions exposed in @mui/system. You can specify any valid CSS using this support, as well as many theme-aware properties unique to MUI System.

jsx
Copy code
<Box component='article' sx={{ px: 4 }} />
jsx
Copy code
<Grid item xs={12} sm={4} md={6} sx={{ order: { xs: 4, sm: 4, md: 3 } }} />
:heavy_check_mark: Reusable Components in React

Example of a Title component:

jsx
Copy code
import { Typography } from '@mui/material';
import React from 'react';

const Title = ({ text, textAlign }) => {
  return (
    <Typography 
      variant='h4'
      component='h3'
      sx={{ fontWeight: '700', textAlign }}
    >
      {text}
    </Typography>
  );
};

export default Title;
:heavy_check_mark: Using Styled-Components with Material UI

Customize the Box component:

jsx
Copy code
const ListMenu = styled(List)(({ theme }) => ({
    display: 'none',
    [theme.breakpoints.up("sm")]: {
        display: "flex",
    },
}));
:heavy_check_mark: Responsive Design and Mobile First

Using Grid in Material UI:

jsx
Copy code
<Grid item xs={12} sm={4} md={6}>
    <img src={imgDetail} alt="" style={{ width: '100%' }} />
</Grid>
:heavy_check_mark: Using Mobile Menu with MUI (Drawer)

Drawer for mobile menu/Hamburger

Dependencies
Material UI v5 - CSS utility packages for layouts.

bash
Copy code
npm install @mui/material @emotion/react @emotion/styled
React Router v6+ - Package for routing in web applications.

bash
Copy code
npm i react-router-dom
React Responsive Carousel v3.2+ - Responsive and customizable carousel for image galleries.

bash
Copy code
npm i react-responsive-carousel
React Animation - Animation for components.

Clone the Repository:
bash
Copy code
git clone https://github.com/username/repository-name.git
Install Dependencies
bash
Copy code
npm install
Run the Application
bash
Copy code
npm start
Open http://localhost:3000

Create Build Folder
bash
Copy code
npm run build
Test the Application:
bash
Copy code
npm test

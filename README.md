# Dental-Clinc
#Source Code

#Header jsx

import React from "react";
import {Link} from 'react-router-dom';
import {Navbar,Nav} from 'react-bootstrap';

function Header (){
    return(
       <Navbar bg = "light" expand = "lg">
        <div className="container">
            <Navbar.Brand as={Link} to ="/">DentalCare</Navbar.Brand>
            <Navbar.Toggle/>
            <Navbar.Collapse>
        <Nav className = 'ms-auto'>
            <Nav.Link as ={Link} to="/Home">Home</Nav.Link>
            <Nav.Link as = {Link} to="/about">About</Nav.Link>
            <Nav.Link as = {Link} to ="/services">Services</Nav.Link>
            <Nav.Link as ={Link} to ="/contact">Contact</Nav.Link>
        </Nav>
        </Navbar.Collapse>
        </div>
       </Navbar> 
    )
}
export default Header;


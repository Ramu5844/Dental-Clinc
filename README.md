# Dental-Clinc
#Source Code

Components
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


#Footer jsx

import React, { Component } from 'react'

class Footer extends Component {
  render() {
    return (
      <div>
        <footer className='bg-light text-center py-4'>
            <p>&copy; 2025 DentalCare Clinic.All rights reserved</p>
        </footer>
        
      </div>
    )
  }
}

export default Footer

#FAQ.jsx

import React from 'react';
import { Accordion } from 'react-bootstrap';

function FAQ(){
    return(
    <section className='my-5'>
        <h2 className='text-center mb-4'>Frequently Asked Questions</h2>
        <Accordion>
            <Accordion.Item eventKey='0'>
                <Accordion.Header>Do I need an appointment?</Accordion.Header>
                <Accordion.Body>Yes,booking in advance is recommended
        
                </Accordion.Body>
            </Accordion.Item>

            <Accordion.Item eventKey='1'>
                <Accordion.Header>Do you accept insurance?</Accordion.Header>
                <Accordion.Body>Yes,we accept most major dental insurance providers.</Accordion.Body>
            </Accordion.Item>
        </Accordion>

    </section>
    )
}
export default FAQ;

pages

Home.jsx


import React from "react";
import { Link } from "react-router-dom";
import { Button } from "react-bootstrap";

function Home(){
    return(
        <>

        <div className="text-center bg-light p-5 rounded">

        <h1>Welcome to DentalCare</h1>
        <p>Your smile,our commitment.</p>
        <Button as={Link} to="/contact">Book Appointment</Button>
        </div>

        <section className="my-5">
            <h2>Our Services</h2>
            <p>We provdie wide range of dental treatment including cosmetic,preventive, and restorative care</p>
             </section>
        </>

    )
}
export default Home

#About.jsx

import React from "react";

function About(){
    return(    
<>
<h2> About Our Clinc</h2>
<p>DentalCare has been serving smiles for over 20 years...</p>

<h3>Our Practitioners</h3>
<p>DR.Smith,Dr.Johson-experienced and compassionate dentists.</p>

<h3>Our Practitioners</h3>

<p>we belive in affordable, high-quality dental care for everyone</p>
</>
    )
}

export default About

Services.jsx

import React from "react";
import {Card, Row, Col} from 'react-bootstrap';


const services = [
    {title:"Teeth Ehitening",desc:"Brigthten your smile.",icon:"🦷"},
    { title: "Dental Implants", desc: "Permanent tooth replacement.", icon: "🛠️" },
  ` { title: "Orthodontics", desc: "Braces & aligners.", icon: "😬" },
    { title: "Root Canal", desc: "Save your natural tooth.", icon: "🧪" },
    { title: "Dental Cleaning", desc: "Preventive oral hygiene.", icon: "🪥" },
    { title: "Cosmetic Dentistry", desc: "Improve smile aesthetics.", icon: "🎨" },
];


function Services(){
    return(
        <>
        <h2 className="text-center mb-4">Our Services</h2>
        <Row>
            {services.map((service,index) => (
                <Col md={4} className="mb-4" key={index}>
                    <Card>
                        <Card.Body>
                            <h4>{service.icon} {service.title}</h4>
                            <p>{service.desc}</p>
                        </Card.Body>

                    </Card>
                </Col>

            ))}
        </Row>
        </>
    )
}

export default Services;


#Contact.jsx

import React,{useState} from "react";
import axios from 'axios';
import {Form, Button} from 'react-bootstrap';


function Contact(){
    const[form,setForm] = useState({
        name:'', email:'', subject:'', message:''
    })
    const handleChange =(e) =>setForm({...form,[e.target.name]:e.target.value});
    const handleSubmit = (e) =>{
        e.preventDefault();
        axios.post('https://example.com/api/contact', form)
        .then(()=> alert('Form submitted (simulated)'))
        .catch(() => alert('Submission failed(simulated)'));
    };
    return(
        <>
        <h2>Contact Us</h2>
        <Form onSubmit={handleSubmit}>
            <Form.Group className="mb-3">
                <Form.Label>Name</Form.Label>
                <Form.Control name="name" onChange={handleChange} required></Form.Control>
            </Form.Group>
            <Form.Group className="mb-3">
                <Form.Label>Email</Form.Label>
                <Form.Control type="email" onChange={handleChange} required></Form.Control>
            </Form.Group>
            <Form.Group className="mb-3">
          <Form.Label>Subject</Form.Label>
          <Form.Control name="subject" onChange={handleChange} required />
        </Form.Group>
        <Form.Group className="mb-3">
          <Form.Label>Message</Form.Label>
          <Form.Control as="textarea" name="message" rows={4} onChange={handleChange} required />
        </Form.Group>
        <Button type="submit">Send</Button>
        </Form>

        <div className="my-4">
            <p>📞 (123) 456-789</p>
            <p>📧 contact@dentalcare.com</p>
        <p>🏢 123 Smile Street, HappyTown</p>
        </div>


        <iframe
            src="https://www.google.com/maps/embed?pb=!1m18..."
            width="100%" height="300" style={{border:0}}
            allowFullScreen loading="lazy">
        </iframe>
        </>
    )
}

export default Contact

index.jsx

import React from 'react';
import ReactDOM from 'react-dom/client';
import './index.css';
import App from './App';
import reportWebVitals from './reportWebVitals';
import 'bootstrap/dist/css/bootstrap.min.css';


const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(
  <React.StrictMode>
    <App />
  </React.StrictMode>
);

// If you want to start measuring performance in your app, pass a function
// to log results (for example: reportWebVitals(console.log))
// or send to an analytics endpoint. Learn more: https://bit.ly/CRA-vitals
reportWebVitals();

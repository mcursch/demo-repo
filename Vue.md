## Component Lifecycle Hooks
Four main phases:
Creation, Mounting, Updating, Unmounting

Hooks allow us to tap into these phases and execute code
There are a total of 13 hooks, but only some are super important

Order of invocation is important

### Creation
beforeCreate(), created()
Data properties and watchers arent processed in beforeCreate method, but are accessible in created() method, so its likely to be used more

API calls from component should be done here

### Mounting
template and html are mounted onto DOM which we see on browser
beforeMount() and mounted(), utilize if dom needs to be modified right before or after rendering

### Updating 
triggered when reactive property changes or component rerenders
beforeUpdate(), updated()
beforeUpdate called when data changes but before DOM is changed
updated is called after patch has been applied to DOM

### Unmounting
Component is about to be removed from DOM
beforeUnmount, unmounted
before is likely used more, used to remove dependencies before removing component

### Misc Methods
Activated, Deactivated, errorCaptured, renderTracked, renderTriggered
active and deactive relate to keepalive for dynamic components

## What is the DOM
Document Object Model

Structure of website organized in doc object

when u inspect, you get html representation of DOM

current status of how browser is interpreting the website

Dom represents documents as nodes and objects
as object oriented rep, allows web page to be modified with scripting langs like JS

### Dom Documents
access the document and window objects to manipulate document itself

More info found here on Document and document functions

https://developer.mozilla.org/en-US/docs/Web/API/Document

### DOM Nodes
Every object within a document is a node of some kind
https://developer.mozilla.org/en-US/docs/Web/API/Node


Common API's in scripting using the DOM

document.querySelector()
document.querySelectorAll()
document.createElement()
Element.innerHTML
Element.setAttribute()
Element.getAttribute()
EventTarget.addEventListener()
HTMLElement.style
Node.appendChild()
window.onload
window.scrollTo()
// define the coffee menu
const menu = [
  {
    name: "Espresso",
    price: 2.50
  },
  {
    name: "Cappuccino",
    price: 3.50
  },
  {
    name: "Latte",
    price: 3.00
  },
  {
    name: "Mocha",
    price: 4.00
  }
];

// display the coffee menu on the website
function displayMenu() {
  const menuContainer = document.getElementById("menu-container");
  
  // clear the current menu
  menuContainer.innerHTML = "";
  
  // create a new menu
  const menuList = document.createElement("ul");
  
  for (let item of menu) {
    const menuItem = document.createElement("li");
    const itemName = document.createElement("h3");
    const itemPrice = document.createElement("span");
    
    itemName.textContent = item.name;
    itemPrice.textContent = `$${item.price.toFixed(2)}`;
    
    menuItem.appendChild(itemName);
    menuItem.appendChild(itemPrice);
    
    menuList.appendChild(menuItem);
  }
  
  menuContainer.appendChild(menuList);
}

// add event listeners to update the menu
const espressoButton = document.getElementById("espresso-button");
const cappuccinoButton = document.getElementById("cappuccino-button");
const latteButton = document.getElementById("latte-button");
const mochaButton = document.getElementById("mocha-button");

espressoButton.addEventListener("click", () => {
  menu[0].price += 0.50;
  displayMenu();
});

cappuccinoButton.addEventListener("click", () => {
  menu[1].price += 0.50;
  displayMenu();
});

latteButton.addEventListener("click", () => {
  menu[2].price += 0.50;
  displayMenu();
});

mochaButton.addEventListener("click", () => {
  menu[3].price += 0.50;
  displayMenu();
});

// display the current date and time on the website
function displayDateTime() {
  const dateTimeContainer = document.getElementById("date-time-container");
  
  const now = new Date();
  const date = now.toLocaleDateString();
  const time = now.toLocaleTimeString();
  
  dateTimeContainer.textContent = `${date} ${time}`;
}

// add event listener to update the date and time
setInterval(() => {
  displayDateTime();
}, 1000);

// handle form submission
function submitForm(event) {
  event.preventDefault();
  
  const nameInput = document.getElementById("name-input");
  const emailInput = document.getElementById("email-input");
  const messageInput = document.getElementById("message-input");
  
  // TODO: send form data to server
}

const form = document.getElementById("contact-form");
form.addEventListener("submit", submitForm);

// display the menu and current date/time when the page loads
window.addEventListener("load", () => {
  displayMenu();
  displayDateTime();
});

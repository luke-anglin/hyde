---
layout: page
title: About
---

 <!-- CSS styles for the pop-up form -->
  <!-- <style>
  .popup-form {
    position: fixed;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    background-color: #fff;
    padding: 20px;
    border-radius: 5px;
    box-shadow: 0px 2px 10px rgba(0, 0, 0, 0.1);
    z-index: 9999;
    text-align: center;
  }

  .popup-form h2 {
    margin-bottom: 10px;
  }

  .popup-form input[type="email"] {
    width: 100%;
    padding: 10px;
    margin-bottom: 10px;
    border: 1px solid #ccc;
    border-radius: 3px;
  }

  .popup-form button {
    padding: 10px 20px;
    background-color: #4CAF50;
    color: #fff;
    border: none;
    border-radius: 3px;
    cursor: pointer;
  }

  .popup-form button.close {
    background-color: #ccc;
    margin-left: 10px;
  }
</style> -->

<p class="message">
  Hey, thanks for stopping by! I'm an engineer who authors books as my passion project. I just wrote a dystopian, fiction novel about the a world taken over by companies after an apocalypse. You can find a summary and more information about my first book, <em>Anaconda's Prime</em> of <em>The Afterburn Trilogy</em>, <a href="{{site.baseurl | append: '/books/'}}">here</a>. 
</p>

![Book Cover Placeholder](https://i.imgur.com/mNtDD5U.jpg)

<p>
  When I'm not writing or programming, I love to play sports! Beach volleyball is certainly my favorite. I'm also trilingual and play the guitar, but my biggest obsession is with my therapy dog Maya!
</p>

![MayaDog](https://i.imgur.com/Ay9UoFj.jpg)

<p>
A little about me - I graduated the University of Virginia's School of Engineering in three years. I previously worked at Tesla as a data scientist, and now I'm working at Ernst & Young.
</p>

<p>
More important than any of that is my family. We're kind of weird. Here are some pictures . . . 
</p>

![Casey](https://i.imgur.com/ASqfbO4.jpg)
![mom](https://i.imgur.com/VoKnZ7E.jpg)
![dad](https://i.imgur.com/Ah9xOS5.jpg)

<p>So yeah! Check out my book or the other links in the sidebar.</p>

![](https://i.pinimg.com/474x/6d/01/da/6d01da006a6a4654ea9943d062307398--so-funny-funny-pics.jpg)

<!-- <div class="card" style="width: 18rem;">
  <div class="card-body">
    <h5 class="card-title">Luke Anglin</h5>
    <p class="card-text">Contact me</p>
  </div>
  <ul class="list-group list-group-flush">
    <li class="list-group-item">Email: lta9vw@virginia.edu</li>
    <li class="list-group-item">Github: luke-anglin</li>
  </ul>
  <div class="card-body">
    <a href="https://github.com/luke-anglin" style="margin-right: 5em;" class="card-link">GitHub</a>
  </div>
</div> -->
<!--
 <div class="popup-form" id="newsletter-popup">
  <h2>Subscribe to our Newsletter</h2>
  <form id="subscribe-form">
    <input type="email" name="email" placeholder="Enter your email" required>
    <br>
    <button type="submit">Subscribe</button>
    <button type="button" class="close" onclick="closePopup()">Close</button>
  </form>
</div>

  <script>
    function closePopup() {
    document.getElementById("newsletter-popup").style.display = "none";
  }

  document.getElementById("subscribe-form").addEventListener("submit", function(event) {
    event.preventDefault();

    var apiKey = "e8e23728eaea379bed9a202ff047002e-us21";
    var listId = "da40f6d9bf";

    var formData = new FormData(this);
    var email = formData.get("email");

    var url = "https://us21.api.mailchimp.com/3.0/lists/" + listId + "/members/";
    var data = {
      email_address: email,
      status: "subscribed",
      merge_fields: {
        FNAME: "First Name",
        LNAME: "Last Name"
    }
    };
    const headers = new Headers();
    headers.append('Authorization', 'Basic ' + btoa('anystring'+ ':' + apiKey));
    headers.append('Content-Type', 'application/json');

    fetch(url, {
      method: "POST",
      headers: headers,
      body: JSON.stringify(data)
    })
      .then(function(response) {
        if (response.ok) {
          // Customize the success action here (e.g., show success message, redirect)
          console.log("Form submitted successfully!");
        } else {
          // Customize the error action here (e.g., show error message)
          console.log("Error submitting form.");
        }
      })
      .catch(function(error) {
        // Customize the error action here (e.g., show error message)
        console.log("Error submitting form:", error);
      });
      document.getElementById("newsletter-popup").style.display = "none";

  });


  // Display the popup form on page load
  window.addEventListener("load", function() {
    document.getElementById("newsletter-popup").style.display = "block";
  });
  </script> -->

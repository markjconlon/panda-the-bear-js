<!-- Hacking Panda the Bear's Resume

Select the element that contains the profile image (hint: look for the class). Change the src attribute so it points to a picture of your choosing instead (hint: use attr()).
PROTIP: use the inspector to learn the dimensions of the current profile image and use a placeholder image service such as Place Bear to get an image of the same size.

Use the same approach to select the element that contains the photo of the sky and change the src attribute to another picture URL of your choosing.

Select the heading that says "Panda the Bear" and change it to your own name. (hint: use text())

Select the heading that says "Employment" and change it to something else. (hint: use a descendant selector)

Panda the Bear is lying about their skills! Take the "time travel" skill off the page to satisfy your personal sense of justice. Use your googling and docs-skimming skillz to find a jQuery function that will allow you to remove elements from the DOM. (hint: there are multiple ways of doing this, but the parent() function might be useful when it comes to selecting the right element)

Change the colour of the body. (hint: use css())

Change the colour used by the highlight class.

Change the font family of the h1 to 'monospace'.

Find a way to select the round icons in the sidebar and then change their colour.

Scroll down to the contact form. Change the placeholder attribute of the name field to "identify yourself".

Change the placeholder attribute of the message field to "state your business".

Give the name field a "value" attribute of "your nemesis".

Change the value attribute of the email field to "koalathebear@gmail.com".

Change the value of the submit button on the contact form to "En garde!".

Bonus points: try experimenting with both the attr() function and the val() function to find different ways of doing this.

We should stop Koala from sending an email to Panda that they might regret! Find a way to disable the submit button (hint: familiarize yourself with the disabled attribute).

We should help Panda protect their privacy by clearing their personal details from the sidebar. You can use empty() to do this.

Adding Elements to the DOM

That drawing of Pikachu is really cute. Let’s duplicate it using clone() and insert it at the bottom of the .portfolio-container using insertAfter() or appendTo().

Wow, that was so satisfying I think we should do it 10 more times. Use a for loop to help you do this.

Let’s add a message about when the page was last updated. We'll do this by appending a new <li> element to the <ul> in the sidebar (you might need to refresh the page to bring back the list items that we emptied out earlier).

screenshot of final effect

document.createElement, document.createTextNode, and appendChild are the keys to this process*.

First we need to construct a new <li> tag.

var listItem = document.createElement('li');

It isn't part of the DOM yet, it's just floating in the void. We'll eventually attach it to the <ul> in the sidebar, below Panda's name, location, and phone number.

Now we need a new <span> tag to go inside the <li> we just made. This span will eventually go in the left column below 'Phone'.

var leftSpan = document.createElement('span');

Next we need to make a "text node" in order to put text inside our new span. A text node is a chunk of plain text that lives inside some HTML tag in the DOM.

var lastUpdated = document.createTextNode('Page last updated on');

We're ready to put that new text node inside our new <span> using appendChild.

leftSpan.appendChild(lastUpdated);

And we'll put the <span> inside the <li>, again using appendChild.

listItem.appendChild(leftSpan);

At this point our new elements are attached to each other but are still floating in the void separate from our webpage's DOM.

It's up to you to go through the same process for the second span that will go in the right-hand column of the <ul> (below Panda's phone number). Look up the docs for the Date class to find a way of displaying the current date inside your next text node.

After that, find a way of selecting the <ul> and append the new <li> to it. For bonus marks, apply the correct classes to these new elements of yours so the styling is consistent with the rest of the list items.

* you may notice that these functions are vanilla JavaScript and do not come from jQuery -->

1)
$('.profile-image').attr('src', 'https://placebear.com/400/400')

2)
$('h1.highlight').text('Mark')

3)
$('#employment > .info-title').text('jobs')

4)
$('#time-travel').parent().remove()

5)
$('body').css('background-color', 'red')

6)
$('.highlight').css('color', 'black')

7)
$('h1').css('font-family', 'monospace')

8)
$('.action-icon-bg').css('background-color', 'blue')

9)
$('form').find('input[name="name"]').attr('placeholder', "identify yourself")

10)
$('form').find('textarea[name="message"]').attr('placeholder', "state your business")

11)
$('form').find('input[name="name"]').attr('value', "Your Nemesis")

12)
$('form').find('input[name="email"]').attr('value', "koalathebear@gmail.com")

13)
$('form').find('input[name="submit"]').attr('value', "En Garde!")

Adding Elements to the DOM

1)
$('#right-image').clone().appendTo('.portfolio-container')

2)
for (i=0; i < 10; i++)$('#right-image').clone().appendTo('.portfolio-container')

final step you just set the element in the void to a variable then use it as needed in this case

  $('.bio-info').append(x)

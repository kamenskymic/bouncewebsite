<div class="columns-container">
{% for event in site.data.about %}
<div class="card-wrapper">
<div class="card">
<div class="bio-img">
<img src="{{ event.img }}" alt="enter img" />
</div>
<div class="container">
<div class="container-content">
<h2>{{ event.name }}</h2>
<p class="title">{{ event.title }}</p>
</div>
<div class="socials">
{% if event.linkedin %}
<a href="{{ event.linkedin }}" target="_blank"><img src="{{ 'assets/img/icon-linkedin.png' }}" alt="LinkedIn icon"></a>
{% endif %}
{% if event.twitter %}
<a href="{{ event.twitter }}" target="_blank"><img src="{{ 'assets/img/icon-twitter.png' }}" alt="Twitter icon"></a>
{% endif %}
</div>
</div>
</div>


<div class="modal">
<div class="modal-outside" data-close></div>
<div class="modal-content">
<span class="close" data-close>&times;</span>
<img src="{{ event.img }}" alt="enter img" />
<div class="container">
<div class="container-content">
<h2>{{ event.name }}</h2>
<p class="title">{{ event.title }}</p>
</div>
<div class="socials">
{% if event.linkedin %}
<a href="{{ event.linkedin }}" target="_blank"><img src="{{ 'assets/img/icon-linkedin.png' }}" alt="LinkedIn icon"></a>
{% endif %}
{% if event.twitter %}
<a href="{{ event.twitter }}" target="_blank"><img src="{{ 'assets/img/icon-twitter.png' }}" alt="Twitter icon"></a>
{% endif %}
</div>
</div>
<p>{{ event.about }}</p>
</div>
</div>
</div>
{% endfor %}
</div>

<script>
var cardWrapperEls = document.getElementsByClassName('card-wrapper');


for (const cardWrapperEl of cardWrapperEls) {
    const cardEl = cardWrapperEl.querySelector(".card");
    const modalEl = cardWrapperEl.querySelector(".modal");
    const modalCloseEls = cardWrapperEl.querySelectorAll("[data-close]");
    const socialEls = cardWrapperEl.querySelectorAll(".socials a");

    cardEl.addEventListener("click", () => {
        modalEl.style.display = "block";
        document.querySelector("body").style.overflow = "hidden";
    })

    for (const socialEl of socialEls) {
        socialEl.addEventListener("click", (event) => {
            event.stopPropagation();
        })
    }

    for (const modalCloseEl of modalCloseEls) {
        modalCloseEl.addEventListener("click", () => {
            modalEl.style.display = "none";
            document.querySelector("body").style.overflow = "visible";
        })
    }
}


</script>
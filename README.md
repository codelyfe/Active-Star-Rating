# Active-Star-Rating
Star rating animation using CSS and JS

## Code
```
   <style>
   .star-rating {
        position: relative;
        display: inline-block;
    }



    @keyframes star-appear {
        0% {
            transform: scale(0.5);
            color: rgba(255, 255, 255, 0.1);
        }
        100% {
            transform: scale(1);
            color: orange;
        }
    }

    .checked {
        color: orange !important;
    }
   </style>
```
```  
    <div class="star-rating">
        <span class="fa fa-star"></span>
        <span class="fa fa-star"></span>
        <span class="fa fa-star"></span>
        <span class="fa fa-star"></span>
        <span class="fa fa-star"></span>
    </div>
```
```
<script>
document.addEventListener("DOMContentLoaded", () => {
    const stars = document.querySelectorAll('.star-rating .fa-star');
    let index = 0;

    function addStar() {
        if (index < stars.length) {
            stars[index].classList.add('checked');
            stars[index].style.color = 'orange';
            index++;
            setTimeout(addStar, 500); // Adjust the timing to control the speed of appearance
        } else {
            index = 0; // Reset index for infinite looping
            setTimeout(() => {
                stars.forEach(star => star.classList.remove('checked'));
                stars.forEach(star => star.style.color = 'rgba(255, 255, 255, 0.1)');
                setTimeout(addStar, 500); // Restart the animation after a short delay
            }, 1000); // Adjust delay before restarting
        }
    }

    addStar();
});
</script>

```

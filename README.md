# Carousels-Effect
Infinite Carousel Effect using CSS and HTML
![Screenshot 2025-06-30 155031](https://github.com/user-attachments/assets/876baa15-dda4-4cd2-a797-9b7ad5690f3d)

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <link rel="stylesheet" href="3D_slider.css">
    <link href="https://fonts.cdnfonts.com/css/ica-rubrik-black" rel="stylesheet">
    <link href="https://fonts.cdnfonts.com/css/poppins" rel="stylesheet">

</head>
<body>
    <div class="main">
        <div class="slider" style="--quantity: 12">
            <div class="image" style="--position: 1"><img src="bmw1.JPG" alt=""></div>
            <div class="image" style="--position: 2"><img src="bmw2.JPG" alt=""></div>
            <div class="image" style="--position: 3"><img src="bmw3.JPG" alt=""></div>
            <div class="image" style="--position: 4"><img src="bmw4.JPG" alt=""></div>
            <div class="image" style="--position: 5"><img src="bmw5.JPG" alt=""></div>
            <div class="image" style="--position: 6"><img src="bmw6.JPG" alt=""></div>
            <div class="image" style="--position: 7"><img src="bmw7.JPG" alt=""></div>
            <div class="image" style="--position: 8"><img src="bmw8.JPG" alt=""></div>
            <div class="image" style="--position: 9"><img src="bmw9.JPG" alt=""></div>
            <div class="image" style="--position: 10"><img src="bmw10.JPG" alt=""></div>
            <div class="image" style="--position: 11"><img src="bmw11.JPG" alt=""></div>
            <div class="image" style="--position: 12"><img src="bmw12.JPG" alt=""></div>
        </div>
        <div class="context">
            <h1 data-content="BMW Classics">BMW Classics</h1>
            <div class="info">
                <p>By Lenin</p>
                <p>Created using only HTML & CSS.</p>
            </div>
        </div>
        <div class="bg"></div>    
    </div>
</body>
</html>

/** CSS CODE **/
* {
    padding: 0;
    margin: 0;
    box-sizing: border-box;
}

body {
    background-color: #D2D2D2;
    background-image: 
    repeating-linear-gradient(
        to right, transparent 0 100px,
        #25283b22 100px 101px
    ),
    repeating-linear-gradient(
        to bottom, transparent 0 100px,
        #25283b22 100px 101px
    );
}
/* body::before{
    position: absolute;
    width: min(1400px, 90vw);
    top: 10%;
    left: 50%;
    height: 90%;
    transform: translateX(-50%);
    content: '';
    background-image: url(27230.jpg);
    background-size: 100%;
    background-repeat: no-repeat;
    background-position: top center;
    pointer-events: none;
} */
.main {
    position: relative;
    text-align: center;
    overflow: hidden;
    width: 100%;
    height: 100vh;
}
.main .slider {
    width: 150px;
    height: 200px;
    position: absolute;
    top: 20%;
    left: calc(50% - 75px);
    transform-style: preserve-3d;
    transform: perspective(5000px);
    animation: autoRun 20s linear infinite;
    z-index: 3;
}
@keyframes autoRun {
    from {
        transform: perspective(5000px) rotateX(-16deg) rotateY(0deg);
    }to {
        transform: perspective(5000px) rotateX(-16deg) rotateY(360deg);
    }
}
.main .slider .image {
    position: absolute;
    inset: 0 0 0 0;
    transform: 
    rotateY(calc( (var(--position) - 1) * (360 /var(--quantity)) * 1deg)) translateZ(550px);
}
.main .slider .image img {
    width: 100%;
    height: 100%;
    object-fit: cover;
}
.main .context {
    position: absolute;
    bottom: 0;
    left: 50%;
    transform: translateX(-50%);
    padding-bottom: 100px;
    height: max-content;
    width: min(1400px, 100vw);
    display: flex;
    flex-wrap: wrap;
    justify-content: space-between;
    align-items: center;
    z-index: 2;
}
.main .context h1 {
    position: relative;
    color: #25283B;
    line-height: 1em;
    font-size: 10em;
}
.main .context h1::after {
    position: absolute;
    inset: 0 0 0 0;
    content: attr(data-content); 
    z-index: 2;
    -webkit-text-stroke: 2px #d2d2d2;
    color: transparent;
}
.main .context .info {
    font-size: 1em;
    font-weight: 500;
    color: #25283B;
}
.main .bg {
    background-image: url(model.png);
    height: 75vh;
    width: 100%;
    bottom: 0;
    left: 0;
    position: absolute;
    background-position: top center;
    background-size: auto 130%;
    background-repeat: no-repeat;
    z-index: 1;
}
@media  screen and (max-width: 1023px) {
    .main .slider {
        width: 100px;
        height: 150px;
        left: calc(50% - 50px);
    }
    .main .context h1 {
        font-size: 5em;
        width: 100%;
        text-align: center;
        bottom: 10%;
    }
    .main .slider .image {
        transform: 
        rotateY(calc( (var(--position) - 1) * (360 /var(--quantity)) * 1deg)) translateZ(300px);
    }
    .main .context .info {
        font-size: 0.5em;
        font-weight: 300;
        color: #d2d2d2;
    }
}
@media  screen and (max-width: 767px) {
    .main .slider {
        width: 50px;
        height: 100px;
        left: calc(50% - 25px);
    }
    .main .context h1 {
        font-size: 2em;
        width: 100%;
        text-align: center;
        bottom: 10%;
    }
    .main .slider .image {
        transform: 
        rotateY(calc( (var(--position) - 1) * (360 /var(--quantity)) * 1deg)) translateZ(180px);
    }
    .main .context h1::after {
        -webkit-text-stroke: 0.5px #d2d2d2;
    }
    .main .context .info {
        font-size: 0.2em;
        font-weight: 100;
        color: #d2d2d2;
    }
}

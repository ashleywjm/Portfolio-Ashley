<template>
  <div class="ticket-wrapper my-5 d-flex justify-content-center px-3" style="filter: drop-shadow(0 20px 25px rgba(0,0,0,0.15));">
    <div class="vintage-ticket d-flex flex-row text-dark text-start">
      
      <div class="ticket-details d-flex flex-column justify-content-center p-4 p-md-5">
        
        <h1 class="fw-bold dream-font mb-3 massive-name">Ashley Wong</h1>
        
        <div class="d-flex flex-column gap-2 mb-4 ms-1">
          <a href="mailto:ashley.wjm@gmail.com" class="text-decoration-none text-dark fw-bold fs-5 ticket-link">
            📧 ashley.wjm@gmail.com
          </a>
          <a href="https://www.linkedin.com/in/ashley-wong-997b77216" target="_blank" class="text-decoration-none text-dark fw-bold fs-5 ticket-link">
            🔗 LinkedIn
          </a>
        </div>

      </div>

      <div class="ticket-image position-relative border-start border-end border-secondary border-opacity-25 bg-dark">
        <img src="/my_image.png" alt="Ashley Wong" class="ticket-img" style="object-fit: cover;">
      </div>

      <div class="ticket-stub d-flex align-items-center justify-content-center p-3">
        <div class="css-barcode"></div>
      </div>

    </div>
  </div>
</template>

<style scoped>
/* Typography & External Font Import */
@font-face {
  font-family: 'Dream Avenue';
  src: url('../assets/fonts/DreamAvenue.ttf') format('truetype');
  font-weight: normal;
  font-style: normal;
}

.dream-font { font-family: 'Dream Avenue', serif; }
.lh-base { line-height: 1.6 !important; }

/* THE MAGIC: This creates the massive, responsive name! */
.massive-name {
  /* clamp(minimum_size, preferred_viewport_scaling, maximum_size) */
  font-size: clamp(3.5rem, 7vw, 6.5rem) !important;
  line-height: 1.05;
  letter-spacing: -1px; /* Pulls the letters slightly closer for a bolder look */
}

/* Link hover effect */
.ticket-link:hover {
  text-decoration: underline !important;
  color: #000 !important;
}

/* 1. The Main Ticket Container */
.vintage-ticket {
  display: flex !important;
  flex-direction: row !important;
  
  width: 100% !important;
  max-width: 1300px; /* Increased to span the screen */
  height: 500px;     /* Increased slightly to fit the larger text */
  
  background-color: #ECE6E8;
  border-radius: 12px;
  box-shadow: 0 15px 35px rgba(0,0,0,0.15);
  
  -webkit-mask-image: 
    radial-gradient(circle at 85% 0px, transparent 15px, black 16px),
    radial-gradient(circle at 85% 100%, transparent 15px, black 16px);
  -webkit-mask-size: 100% 51%;
  -webkit-mask-position: top, bottom;
  -webkit-mask-repeat: no-repeat;
  
  mask-image: 
    radial-gradient(circle at 85% 0px, transparent 15px, black 16px),
    radial-gradient(circle at 85% 100%, transparent 15px, black 16px);
  mask-size: 100% 51%;
  mask-position: top, bottom;
  mask-repeat: no-repeat;
}

/* 2. Column Widths */
.ticket-details { width: 55%; }
.ticket-image { width: 30%; overflow: hidden; display: flex; align-items: center; justify-content: center; }
.ticket-stub { width: 15%; }

/* Image styling */
.ticket-img {
  width: 100%;
  height: 100%;
  display: block;
}

/* Barcode */
.css-barcode {
  width: 40px;
  height: 350px; /* Made the barcode a bit taller to match the new ticket height */
  background-image: repeating-linear-gradient(
    to right, 
    #222 0px, #222 4px, 
    transparent 4px, transparent 8px, 
    #222 8px, #222 10px, 
    transparent 10px, transparent 14px, 
    #222 14px, #222 20px, 
    transparent 20px, transparent 24px
  );
}

/* 3. Mobile Responsiveness */
@media (max-width: 768px) {
  .vintage-ticket {
    flex-direction: column !important;
    height: auto;
    mask-image: none !important; 
    -webkit-mask-image: none !important;
  }
  .ticket-details, .ticket-image, .ticket-stub { width: 100%; }
  .ticket-image { 
    height: 300px; 
    border-left: none !important;
    border-right: none !important;
    border-top: 1px solid rgba(0,0,0,0.1);
    border-bottom: 1px solid rgba(0,0,0,0.1);
  }
  .ticket-stub {
    border-top: 2px dashed #a8a096;
    height: 120px;
  }
  .css-barcode {
    width: 200px;
    height: 40px;
    background-image: repeating-linear-gradient(
      to bottom, 
      #222 0px, #222 4px, transparent 4px, transparent 8px, #222 8px, #222 10px, transparent 10px, transparent 14px, #222 14px, #222 20px, transparent 20px, transparent 24px
    );
  }
}
</style>
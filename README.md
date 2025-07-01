<div align="center">

<svg width="400" height="400" viewBox="-200 -200 400 400" xmlns="http://www.w3.org/2000/svg">
  <defs>
    <!-- Define gradients for depth effect -->
    <linearGradient id="grad1" x1="0%" y1="0%" x2="100%" y2="100%">
      <stop offset="0%" style="stop-color:#ff6b6b;stop-opacity:1" />
      <stop offset="100%" style="stop-color:#4ecdc4;stop-opacity:1" />
    </linearGradient>
    <linearGradient id="grad2" x1="100%" y1="0%" x2="0%" y2="100%">
      <stop offset="0%" style="stop-color:#45b7d1;stop-opacity:1" />
      <stop offset="100%" style="stop-color:#96ceb4;stop-opacity:1" />
    </linearGradient>
    <linearGradient id="grad3" x1="50%" y1="0%" x2="50%" y2="100%">
      <stop offset="0%" style="stop-color:#f7b731;stop-opacity:1" />
      <stop offset="100%" style="stop-color:#eb3b5a;stop-opacity:1" />
    </linearGradient>
    <radialGradient id="grad4">
      <stop offset="0%" style="stop-color:#a55eea;stop-opacity:1" />
      <stop offset="100%" style="stop-color:#5f3dc4;stop-opacity:1" />
    </radialGradient>
    
    <!-- Filters for 3D effects -->
    <filter id="blur">
      <feGaussianBlur in="SourceGraphic" stdDeviation="2" />
    </filter>
  </defs>

  <!-- Container for the entire animation -->
  <g id="dodecahedron">
    <!-- Bouncing animation with ease -->
    <animateTransform
      attributeName="transform"
      type="translate"
      values="0,0; 0,-60; 0,-55; 0,-60; 0,0"
      dur="2.5s"
      repeatCount="indefinite"/>
    
    <!-- Main rotation container -->
    <g>
      <!-- X-axis rotation -->
      <animateTransform
        attributeName="transform"
        type="rotate"
        values="0 1 0; 360 1 0"
        dur="7s"
        repeatCount="indefinite"/>
      
      <!-- Y-axis rotation container -->
      <g>
        <animateTransform
          attributeName="transform"
          type="rotate"
          values="0 0 1; 360 0 1"
          dur="11s"
          repeatCount="indefinite"
          additive="sum"/>
        
        <!-- Z-axis rotation and perspective container -->
        <g>
          <animateTransform
            attributeName="transform"
            type="rotate"
            from="0 0 0"
            to="360 0 0"
            dur="13s"
            repeatCount="indefinite"
            additive="sum"/>
          
          <!-- Perspective simulation using scale -->
          <animateTransform
            attributeName="transform"
            type="scale"
            values="1,1; 0.8,0.8; 1,1; 1.2,1.2; 1,1"
            dur="5s"
            repeatCount="indefinite"
            additive="sum"/>
          
          <!-- Small Stellated Dodecahedron faces with 3D arrangement -->
          
          <!-- Front faces -->
          <g transform="translateZ(50)">
            <!-- Face 1 - Front pentagram -->
            <g transform="rotate(0 0 0)">
              <polygon points="0,-80 16,-24 76,-25 29,10 47,65 0,32 -47,65 -29,10 -76,-25 -16,-24"
                       fill="url(#grad1)" 
                       stroke="#333" 
                       stroke-width="1.5" 
                       opacity="0.9">
                <animate attributeName="opacity" 
                         values="0.9;0.4;0.9" 
                         dur="4s" 
                         repeatCount="indefinite"/>
                <animateTransform
                  attributeName="transform"
                  type="scale"
                  values="1,1; 1.1,1.1; 1,1"
                  dur="3s"
                  repeatCount="indefinite"/>
              </polygon>
            </g>
            
            <!-- Face 2 -->
            <g transform="rotate(72 0 0)">
              <polygon points="0,-80 16,-24 76,-25 29,10 47,65 0,32 -47,65 -29,10 -76,-25 -16,-24"
                       fill="url(#grad2)" 
                       stroke="#333" 
                       stroke-width="1.5" 
                       opacity="0.8">
                <animate attributeName="opacity" 
                         values="0.8;0.3;0.8" 
                         dur="4s" 
                         begin="0.8s"
                         repeatCount="indefinite"/>
                <animateTransform
                  attributeName="transform"
                  type="scale"
                  values="1,1; 1.15,1.15; 1,1"
                  dur="3s"
                  begin="0.5s"
                  repeatCount="indefinite"/>
              </polygon>
            </g>
          </g>
          
          <!-- Side faces with perspective -->
          <g transform="rotateY(60)">
            <!-- Face 3 -->
            <g transform="rotate(144 0 0)">
              <polygon points="0,-75 15,-23 71,-23 27,9 44,61 0,30 -44,61 -27,9 -71,-23 -15,-23"
                       fill="url(#grad3)" 
                       stroke="#333" 
                       stroke-width="1.2" 
                       opacity="0.7">
                <animate attributeName="opacity" 
                         values="0.7;0.2;0.7" 
                         dur="4s" 
                         begin="1.6s"
                         repeatCount="indefinite"/>
                <animateTransform
                  attributeName="transform"
                  type="skewX"
                  values="0; 5; 0; -5; 0"
                  dur="6s"
                  repeatCount="indefinite"/>
              </polygon>
            </g>
            
            <!-- Face 4 -->
            <g transform="rotate(216 0 0)">
              <polygon points="0,-75 15,-23 71,-23 27,9 44,61 0,30 -44,61 -27,9 -71,-23 -15,-23"
                       fill="url(#grad4)" 
                       stroke="#333" 
                       stroke-width="1.2" 
                       opacity="0.6">
                <animate attributeName="opacity" 
                         values="0.6;0.2;0.6" 
                         dur="4s" 
                         begin="2.4s"
                         repeatCount="indefinite"/>
                <animateTransform
                  attributeName="transform"
                  type="skewY"
                  values="0; -3; 0; 3; 0"
                  dur="5s"
                  repeatCount="indefinite"/>
              </polygon>
            </g>
          </g>
          
          <!-- Back faces with blur for depth -->
          <g transform="rotateY(180)" filter="url(#blur)">
            <!-- Face 5 -->
            <g transform="rotate(288 0 0)">
              <polygon points="0,-70 14,-21 66,-22 25,8 41,57 0,28 -41,57 -25,8 -66,-22 -14,-21"
                       fill="url(#grad1)" 
                       stroke="#333" 
                       stroke-width="1" 
                       opacity="0.5">
                <animate attributeName="opacity" 
                         values="0.5;0.1;0.5" 
                         dur="4s" 
                         begin="3.2s"
                         repeatCount="indefinite"/>
              </polygon>
            </g>
            
            <!-- Face 6 -->
            <g transform="rotate(36 0 0)">
              <polygon points="0,-70 14,-21 66,-22 25,8 41,57 0,28 -41,57 -25,8 -66,-22 -14,-21"
                       fill="url(#grad3)" 
                       stroke="#333" 
                       stroke-width="1" 
                       opacity="0.4">
                <animate attributeName="opacity" 
                         values="0.4;0.1;0.4" 
                         dur="4s" 
                         begin="1s"
                         repeatCount="indefinite"/>
              </polygon>
            </g>
          </g>
          
          <!-- Additional stellated points for 3D effect -->
          <g transform="rotateX(45)">
            <polygon points="0,-90 10,-30 50,-31 20,5 30,50 0,25 -30,50 -20,5 -50,-31 -10,-30"
                     fill="url(#grad2)" 
                     stroke="#333" 
                     stroke-width="0.8" 
                     opacity="0.6">
              <animate attributeName="opacity" 
                       values="0.6;0.2;0.6" 
                       dur="3s" 
                       repeatCount="indefinite"/>
              <animateTransform
                attributeName="transform"
                type="rotate"
                from="0 0 0"
                to="360 0 0"
                dur="17s"
                repeatCount="indefinite"/>
            </polygon>
          </g>
          
          <!-- Complex rotation pattern -->
          <animateTransform
            attributeName="transform"
            type="rotate"
            values="0 0.7 0.7; 180 0.7 0.7; 360 0.7 0.7"
            dur="9s"
            repeatCount="indefinite"
            additive="sum"/>
        </g>
      </g>
    </g>
  </g>
  
  <!-- Dynamic shadow with perspective -->
  <ellipse cx="0" cy="150" rx="80" ry="25" fill="#000" opacity="0.3">
    <animate attributeName="rx" 
             values="80;60;80;100;80" 
             dur="2.5s" 
             repeatCount="indefinite"/>
    <animate attributeName="ry" 
             values="25;15;25;35;25" 
             dur="2.5s" 
             repeatCount="indefinite"/>
    <animate attributeName="opacity" 
             values="0.3;0.15;0.3;0.4;0.3" 
             dur="2.5s" 
             repeatCount="indefinite"/>
    <animateTransform
      attributeName="transform"
      type="skewX"
      values="0; 10; 0; -10; 0"
      dur="7s"
      repeatCount="indefinite"/>
  </ellipse>
  
  <!-- Ambient particles for depth -->
  <circle cx="-150" cy="-150" r="2" fill="#fff" opacity="0.6">
    <animate attributeName="opacity" 
             values="0.6;0;0.6" 
             dur="3s" 
             repeatCount="indefinite"/>
    <animateTransform
      attributeName="transform"
      type="translate"
      values="0,0; 300,300; 0,0"
      dur="8s"
      repeatCount="indefinite"/>
  </circle>
  <circle cx="150" cy="-150" r="1.5" fill="#fff" opacity="0.5">
    <animate attributeName="opacity" 
             values="0.5;0;0.5" 
             dur="4s" 
             begin="1s"
             repeatCount="indefinite"/>
    <animateTransform
      attributeName="transform"
      type="translate"
      values="0,0; -300,300; 0,0"
      dur="9s"
      repeatCount="indefinite"/>
  </circle>
</svg>

</div>


<svg xmlns="http://www.w3.org/2000/svg" width="1200" height="420" viewBox="0 0 1200 420" fill="none" role="img" aria-label="Animated penguins with snow, moon, water, aurora and igloos">
  <foreignObject width="100%" height="100%">
    <div xmlns="http://www.w3.org/1999/xhtml">
      <style>
        :root{
          --sky1:#7dd3fc;
          --sky2:#60a5fa;
          --sky3:#1d4ed8;

          --water1:#0ea5e9;
          --water2:#0369a1;

          --snow:#f8fafc;
          --snow2:#e2e8f0;

          --igloo:#e5e7eb;
          --igloo2:#cbd5e1;

          --penguin:#0b1220;
          --belly:#f8fafc;
          --beak:#f59e0b;
          --cheek:#fb7185;

          --shadow: rgba(2, 6, 23, .18);
        }

        @media (prefers-color-scheme: dark){
          :root{
            --sky1:#0b1020;
            --sky2:#101a36;
            --sky3:#111827;

            --water1:#075985;
            --water2:#0b3b5a;

            --snow:#e5e7eb;
            --snow2:#cbd5e1;

            --shadow: rgba(0, 0, 0, .35);
          }
        }

        @media (prefers-reduced-motion: reduce){
          *{ animation: none !important; transition: none !important; }
        }

        .stage{
          width: 100%;
          height: 420px;
          position: relative;
          overflow: hidden;
          border-radius: 18px;
          background: linear-gradient(180deg, var(--sky1) 0%, var(--sky2) 46%, var(--sky3) 100%);
          font-family: ui-sans-serif, system-ui, -apple-system, Segoe UI, Roboto, Helvetica, Arial, "Apple Color Emoji","Segoe UI Emoji";
        }

        /* === Aurora === */
        .aurora{
          position:absolute;
          inset:-80px -25% auto -25%;
          height: 360px;
          width:150%;
          pointer-events:none;
          opacity:.55;
          mix-blend-mode: screen;
          filter: blur(28px) saturate(1.25);
          background:
            radial-gradient(1200px 220px at 20% 35%, rgba(34,197,94,.42), transparent 65%),
            radial-gradient(900px 200px at 55% 30%, rgba(56,189,248,.38), transparent 62%),
            radial-gradient(1000px 220px at 85% 38%, rgba(167,139,250,.36), transparent 65%),
            linear-gradient(90deg, transparent 0%, rgba(34,197,94,.26) 20%, rgba(56,189,248,.22) 48%, rgba(167,139,250,.20) 72%, transparent 100%);
          animation: auroraShift 18s ease-in-out infinite alternate;
          z-index: 1;
        }
        .aurora2{
          position:absolute;
          inset:-120px -30% auto -30%;
          height: 420px;
          width:160%;
          pointer-events:none;
          opacity:.32;
          mix-blend-mode: screen;
          filter: blur(34px) saturate(1.35);
          background:
            radial-gradient(1100px 260px at 30% 35%, rgba(16,185,129,.28), transparent 70%),
            radial-gradient(900px 260px at 70% 34%, rgba(236,72,153,.20), transparent 72%),
            linear-gradient(90deg, transparent 0%, rgba(59,130,246,.18) 28%, rgba(34,197,94,.20) 52%, rgba(167,139,250,.18) 76%, transparent 100%);
          animation: auroraShift2 26s ease-in-out infinite alternate;
          z-index: 1;
        }
        @keyframes auroraShift{
          0%   { transform: translateX(-6%) skewX(-10deg) translateY(0);   filter: blur(28px) saturate(1.2) hue-rotate(0deg); }
          50%  { transform: translateX(2%)  skewX(6deg)  translateY(10px); filter: blur(30px) saturate(1.35) hue-rotate(18deg); }
          100% { transform: translateX(7%)  skewX(12deg) translateY(2px);  filter: blur(28px) saturate(1.25) hue-rotate(-10deg); }
        }
        @keyframes auroraShift2{
          0%   { transform: translateX(5%)  skewX(10deg)  translateY(6px);  filter: blur(34px) saturate(1.3) hue-rotate(10deg); }
          50%  { transform: translateX(-2%) skewX(-6deg)  translateY(0);    filter: blur(36px) saturate(1.45) hue-rotate(-12deg); }
          100% { transform: translateX(-7%) skewX(-12deg) translateY(10px); filter: blur(34px) saturate(1.35) hue-rotate(24deg); }
        }

        /* Clouds */
        .cloud{
          position:absolute;
          top: 34px;
          width: 220px;
          height: 66px;
          opacity: .22;
          filter: blur(.2px);
          background:
            radial-gradient(circle at 25% 55%, rgba(255,255,255,.95) 0 32px, transparent 33px),
            radial-gradient(circle at 45% 40%, rgba(255,255,255,.92) 0 40px, transparent 41px),
            radial-gradient(circle at 65% 55%, rgba(255,255,255,.9) 0 34px, transparent 35px),
            radial-gradient(circle at 80% 60%, rgba(255,255,255,.85) 0 26px, transparent 27px);
          z-index: 6;
        }
        .cloud.c1{ left:-260px; top:42px; animation: drift 34s linear infinite; }
        .cloud.c2{ left:-320px; top:92px; transform: scale(.78); opacity:.18; animation: drift 48s linear infinite; }
        .cloud.c3{ left:-280px; top:18px; transform: scale(.58); opacity:.14; animation: drift 62s linear infinite; }
        @keyframes drift{
          from{ transform: translateX(-140px) scale(var(--s,1)); }
          to{ transform: translateX(1540px) scale(var(--s,1)); }
        }
        .cloud.c1{ --s: 1; }
        .cloud.c2{ --s: .78; }
        .cloud.c3{ --s: .58; }

        /* Moon */
        .moon{
          position:absolute;
          right: 56px;
          top: 34px;
          width: 110px;
          height: 110px;
          border-radius: 999px;
          background:
            radial-gradient(circle at 32% 30%, rgba(255,255,255,.95) 0 26px, rgba(255,255,255,.0) 27px),
            radial-gradient(circle at 38% 38%, #f1f5f9 0 58px, #cbd5e1 59px 100%);
          box-shadow:
            0 14px 36px rgba(0,0,0,.18),
            0 0 0 10px rgba(255,255,255,.06),
            0 0 28px rgba(255,255,255,.12);
          animation: moonFloat 5.2s ease-in-out infinite;
          z-index: 7;
        }
        .moon::before{
          content:"";
          position:absolute;
          inset: 18px;
          border-radius: 999px;
          background:
            radial-gradient(circle at 25% 30%, rgba(148,163,184,.55) 0 6px, transparent 7px),
            radial-gradient(circle at 60% 42%, rgba(148,163,184,.45) 0 8px, transparent 9px),
            radial-gradient(circle at 48% 65%, rgba(148,163,184,.40) 0 7px, transparent 8px),
            radial-gradient(circle at 72% 70%, rgba(148,163,184,.35) 0 5px, transparent 6px);
          opacity:.9;
          mix-blend-mode: multiply;
        }
        @keyframes moonFloat{
          0%,100%{ transform: translateY(0); }
          50%{ transform: translateY(-3px); }
        }

        /* Water */
        .water{
          position:absolute;
          left:0; right:0;
          bottom: 92px;
          height: 98px;
          background: linear-gradient(180deg, var(--water1), var(--water2));
          opacity: .92;
          clip-path: polygon(0 18%, 8% 14%, 16% 18%, 24% 13%, 32% 18%, 40% 12%, 48% 18%, 56% 13%, 64% 18%, 72% 12%, 80% 18%, 88% 13%, 96% 18%, 100% 16%, 100% 100%, 0 100%);
          z-index: 2;
        }
        .water::before{
          content:"";
          position:absolute;
          inset: 0;
          background:
            radial-gradient(circle at 10% 45%, rgba(255,255,255,.22) 0 10px, transparent 11px),
            radial-gradient(circle at 22% 65%, rgba(255,255,255,.18) 0 9px, transparent 10px),
            radial-gradient(circle at 40% 55%, rgba(255,255,255,.20) 0 12px, transparent 13px),
            radial-gradient(circle at 58% 70%, rgba(255,255,255,.18) 0 9px, transparent 10px),
            radial-gradient(circle at 76% 55%, rgba(255,255,255,.20) 0 12px, transparent 13px),
            radial-gradient(circle at 92% 68%, rgba(255,255,255,.16) 0 9px, transparent 10px);
          animation: shimmer 4.8s ease-in-out infinite;
          opacity: .9;
        }
        @keyframes shimmer{
          0%,100%{ transform: translateX(0); opacity:.85; }
          50%{ transform: translateX(18px); opacity:1; }
        }

        /* Snow ground */
        .snow{
          position:absolute;
          left:0; right:0;
          bottom:0;
          height: 120px;
          background: linear-gradient(180deg, var(--snow) 0%, var(--snow2) 100%);
          clip-path: polygon(0 24%, 7% 18%, 14% 24%, 21% 16%, 28% 24%, 35% 18%, 42% 24%, 49% 16%, 56% 24%, 63% 18%, 70% 24%, 77% 16%, 84% 24%, 91% 18%, 100% 24%, 100% 100%, 0 100%);
          box-shadow: 0 -10px 24px rgba(0,0,0,.06) inset;
          z-index: 3;
        }

        /* Snowflakes */
        .flake{
          position:absolute;
          top:-12px;
          width: 6px;
          height: 6px;
          border-radius: 999px;
          background: rgba(255,255,255,.75);
          box-shadow: 0 0 0 2px rgba(255,255,255,.10);
          animation: fall linear infinite;
          opacity: .85;
          z-index: 9;
        }
        @keyframes fall{
          from{ transform: translateY(-30px); }
          to{ transform: translateY(470px); }
        }

        /* Igloos */
        .igloo{
          position:absolute;
          bottom: 76px;
          width: 190px;
          height: 125px;
          border-radius: 200px 200px 34px 34px;
          background: linear-gradient(180deg, var(--igloo) 0%, var(--igloo2) 100%);
          box-shadow: 0 18px 30px var(--shadow);
          overflow:hidden;
          z-index: 4;
        }
        .igloo::before{
          content:"";
          position:absolute;
          inset: 16px 14px 10px 14px;
          border-radius: 180px 180px 28px 28px;
          background:
            linear-gradient(90deg, rgba(15,23,42,.10), rgba(255,255,255,.35)),
            repeating-linear-gradient(0deg, rgba(15,23,42,.08) 0 2px, transparent 2px 14px);
          opacity:.55;
          mix-blend-mode: multiply;
        }
        .igloo .door{
          position:absolute;
          bottom: 0;
          left: 34px;
          width: 62px;
          height: 72px;
          border-radius: 60px 60px 14px 14px;
          background: radial-gradient(circle at 40% 30%, rgba(255,255,255,.22), rgba(15,23,42,.22));
          box-shadow: inset 0 10px 16px rgba(0,0,0,.15);
        }
        .igloo .door::after{
          content:"";
          position:absolute;
          left: 10px; right:10px;
          top: 12px;
          height: 6px;
          border-radius: 999px;
          background: rgba(255,255,255,.18);
        }
        .igloo.i1{ left: 74px; transform: scale(.95); }
        .igloo.i2{ left: 290px; bottom: 72px; transform: scale(.72); opacity:.95; }
        .igloo.i3{ right: 280px; bottom: 74px; transform: scale(.82); opacity:.95; }
        .igloo.i4{ right: 90px; transform: scale(.98); }

        /* Penguins movement (NO scaling) */
        .penguin{
          position:absolute;
          bottom: 56px;
          width: 70px;
          height: 78px;
          transform-origin: 50% 100%;
          animation: run var(--t,16s) linear infinite;
          z-index: 5;
          filter: drop-shadow(0 12px 10px rgba(0,0,0,.20));
        }
        .penguin.rev{
          animation: runBack var(--t,17s) linear infinite;
          transform: scaleX(-1);
        }
        @keyframes run{
          0%{ left: -90px; }
          100%{ left: calc(100% + 90px); }
        }
        @keyframes runBack{
          0%{ left: calc(100% + 90px); }
          100%{ left: -90px; }
        }

        /* One penguin stops sometimes */
        .penguin.pwave{ animation: runStop var(--t,18s) linear infinite; }
        @keyframes runStop{
          0%   { left: -90px; }
          40%  { left: 45%; }
          55%  { left: 45%; }
          100% { left: calc(100% + 90px); }
        }

        /* bob = only Y */
        .pbody{
          position:absolute;
          inset:0;
          transform-origin: 50% 100%;
          animation: bobSlow 1100ms ease-in-out infinite;
        }
        .penguin.rev .pbody{ animation-duration: 1200ms; }
        @keyframes bobSlow{
          0%,100%{ transform: translateY(0); }
          50%{ transform: translateY(1px); }
        }

        /* Footprints: behind penguin */
        .tracks{
          position:absolute;
          bottom: -12px;
          width: 190px;
          height: 16px;
          pointer-events:none;
          z-index: 0;
          opacity: .70;
          filter: blur(.14px);
          background:
            radial-gradient(ellipse 7px 3.6px at 18px 12px, rgba(2,6,23,.18) 0 70%, transparent 72%),
            radial-gradient(ellipse 7px 3.6px at 44px 13px, rgba(2,6,23,.16) 0 70%, transparent 72%),
            radial-gradient(ellipse 2.4px 1.8px at 14px 9px, rgba(2,6,23,.10) 0 78%, transparent 80%),
            radial-gradient(ellipse 2.4px 1.8px at 48px 10px, rgba(2,6,23,.09) 0 78%, transparent 80%);
          background-repeat: repeat-x;
          background-size: 84px 16px;
          background-position: 0 0;
        }
        .penguin .tracks{
          left: -190px;
          -webkit-mask-image: linear-gradient(90deg, transparent 0%, rgba(0,0,0,.15) 35%, rgba(0,0,0,.7) 70%, #000 100%);
          mask-image: linear-gradient(90deg, transparent 0%, rgba(0,0,0,.15) 35%, rgba(0,0,0,.7) 70%, #000 100%);
          transform-origin: 100% 50%;
          animation: tracksFadeL 1.9s linear infinite;
        }
        @keyframes tracksFadeL{
          0%   { opacity:.70; filter: blur(.10px); transform: translateX(0);      background-position: 0 0; }
          100% { opacity:.45; filter: blur(.55px); transform: translateX(-12px); background-position: -84px 0; }
        }

        /* Penguin drawing */
        .body{
          position:absolute;
          inset: 0;
          border-radius: 40px 40px 30px 30px;
          background: linear-gradient(180deg, rgba(255,255,255,.08), rgba(0,0,0,0)) , var(--penguin);
        }
        .belly{
          position:absolute;
          left: 12px;
          right: 12px;
          bottom: 8px;
          top: 16px;
          border-radius: 34px 34px 26px 26px;
          background: linear-gradient(180deg, var(--belly), rgba(226,232,240,.9));
          box-shadow: inset 0 6px 14px rgba(2,6,23,.10);
        }
        .eye{
          position:absolute;
          top: 20px;
          width: 10px;
          height: 10px;
          border-radius: 999px;
          background: #fff;
          box-shadow: inset -2px -2px 0 rgba(0,0,0,.28);
        }
        .eye::after{
          content:"";
          position:absolute;
          width: 4px;
          height: 4px;
          border-radius: 999px;
          background: #0b1220;
          top: 3px;
          left: 3px;
        }
        .eye.l{ left: 20px; }
        .eye.r{ right: 20px; }

        .cheek{
          position:absolute;
          top: 34px;
          width: 10px; height: 8px;
          border-radius: 999px;
          background: rgba(251,113,133,.35);
          filter: blur(.1px);
        }
        .cheek.l{ left: 14px; }
        .cheek.r{ right: 14px; }

        .beak{
          position:absolute;
          left: 50%;
          top: 36px;
          width: 16px;
          height: 12px;
          transform: translateX(-50%);
          background: linear-gradient(180deg, var(--beak), #d97706);
          clip-path: polygon(0 20%, 50% 100%, 100% 20%, 50% 0);
          border-radius: 3px;
        }

        .wing{
          position:absolute;
          top: 38px;
          width: 22px;
          height: 36px;
          border-radius: 999px;
          background: rgba(2,6,23,.72);
          transform-origin: 50% 10%;
          animation: flap 520ms ease-in-out infinite;
        }
        .wing.l{ left: -6px; transform: rotate(18deg); }
        .wing.r{ right: -6px; transform: rotate(-18deg); }

        .foot{
          position:absolute;
          bottom: -6px;
          width: 16px; height: 10px;
          border-radius: 999px;
          background: linear-gradient(180deg, #fbbf24, #f59e0b);
          box-shadow: 0 6px 10px rgba(0,0,0,.18);
          transform-origin: 50% 50%;
        }
        .foot.l{ left: 16px; animation: step 320ms ease-in-out infinite; }
        .foot.r{ right: 16px; animation: step 320ms ease-in-out infinite reverse; }

        @keyframes flap{
          0%,100%{ transform: rotate(var(--wr, -18deg)) translateY(0); }
          50%{ transform: rotate(calc(var(--wr, -18deg) * -1)) translateY(1px); }
        }
        .wing.l{ --wr: 18deg; }
        .wing.r{ --wr: -18deg; }

        @keyframes step{
          0%,100%{ transform: rotate(8deg) translateY(0); }
          50%{ transform: rotate(-10deg) translateY(1px); }
        }

        /* === WAVE: raise wing UP, then small side-to-side wiggle while raised === */
        .penguin.pwave .wing.r{
          animation: raiseAndWave var(--t,18s) ease-in-out infinite;
          transform-origin: 55% 12%;
        }
        @keyframes raiseAndWave{
          0%,39% { transform: rotate(-18deg) translateY(0); }

          /* raise */
          40%    { transform: rotate(-18deg) translateY(0); }
          43%    { transform: rotate(-118deg) translateY(-2px); }

          /* wave (small wiggle while arm is up) */
          46%    { transform: rotate(-98deg)  translateY(-2px); }
          49%    { transform: rotate(-124deg) translateY(-2px); }
          52%    { transform: rotate(-102deg) translateY(-2px); }
          54%    { transform: rotate(-120deg) translateY(-2px); }

          /* return */
          55%    { transform: rotate(-18deg) translateY(0); }
          100%   { transform: rotate(-18deg) translateY(0); }
        }

        /* Penguins timing */
        .p1{ --t: 16.8s; bottom: 54px; }
        .p2{ --t: 15.2s; bottom: 58px; }
        .p3{ --t: 18.0s; bottom: 52px; opacity:.98; }
        .p4{ --t: 14.6s; bottom: 60px; }
        .p5{ --t: 19.2s; bottom: 50px; opacity:.95; }
        .p6{ --t: 15.8s; bottom: 56px; }

        /* Badge */
        .badge{
          position:absolute;
          left: 18px;
          top: 16px;
          padding: 10px 12px;
          border-radius: 14px;
          background: rgba(255,255,255,.16);
          border: 1px solid rgba(255,255,255,.18);
          backdrop-filter: blur(6px);
          color: rgba(255,255,255,.92);
          box-shadow: 0 10px 22px rgba(0,0,0,.16);
          max-width: 60%;
          z-index: 8;
        }
        .badge strong{ display:block; font-size: 14px; letter-spacing:.2px; }
        .badge span{ display:block; font-size: 12px; opacity:.9; margin-top:2px; }
      </style>

      <div class="stage">
        <div class="aurora" aria-hidden="true"></div>
        <div class="aurora2" aria-hidden="true"></div>

        <div class="cloud c1"></div>
        <div class="cloud c2"></div>
        <div class="cloud c3"></div>

        <div class="badge">
          <strong>Linux vibes: penguins on the run</strong>
          <span>snow • sky • moon • water • igloos</span>
        </div>

        <div class="moon" aria-hidden="true"></div>

        <div class="water" aria-hidden="true"></div>

        <div class="igloo i1" aria-hidden="true"><div class="door"></div></div>
        <div class="igloo i2" aria-hidden="true"><div class="door"></div></div>
        <div class="igloo i3" aria-hidden="true"><div class="door"></div></div>
        <div class="igloo i4" aria-hidden="true"><div class="door"></div></div>

        <!-- Penguins -->
        <div class="penguin p1" style="animation-delay:-1.2s;">
          <div class="tracks" aria-hidden="true"></div>
          <div class="pbody">
            <div class="body"></div><div class="belly"></div>
            <div class="wing l"></div><div class="wing r"></div>
            <div class="eye l"></div><div class="eye r"></div>
            <div class="cheek l"></div><div class="cheek r"></div>
            <div class="beak"></div>
            <div class="foot l"></div><div class="foot r"></div>
          </div>
        </div>

        <div class="penguin rev p2" style="animation-delay:-3.6s;">
          <div class="tracks" aria-hidden="true"></div>
          <div class="pbody">
            <div class="body"></div><div class="belly"></div>
            <div class="wing l"></div><div class="wing r"></div>
            <div class="eye l"></div><div class="eye r"></div>
            <div class="cheek l"></div><div class="cheek r"></div>
            <div class="beak"></div>
            <div class="foot l"></div><div class="foot r"></div>
          </div>
        </div>

        <!-- Stops and waves -->
        <div class="penguin p3 pwave" style="animation-delay:-6.1s;">
          <div class="tracks" aria-hidden="true"></div>
          <div class="pbody">
            <div class="body"></div><div class="belly"></div>
            <div class="wing l"></div><div class="wing r"></div>
            <div class="eye l"></div><div class="eye r"></div>
            <div class="cheek l"></div><div class="cheek r"></div>
            <div class="beak"></div>
            <div class="foot l"></div><div class="foot r"></div>
          </div>
        </div>

        <div class="penguin rev p4" style="animation-delay:-2.4s;">
          <div class="tracks" aria-hidden="true"></div>
          <div class="pbody">
            <div class="body"></div><div class="belly"></div>
            <div class="wing l"></div><div class="wing r"></div>
            <div class="eye l"></div><div class="eye r"></div>
            <div class="cheek l"></div><div class="cheek r"></div>
            <div class="beak"></div>
            <div class="foot l"></div><div class="foot r"></div>
          </div>
        </div>

        <div class="penguin p5" style="animation-delay:-8.0s;">
          <div class="tracks" aria-hidden="true"></div>
          <div class="pbody">
            <div class="body"></div><div class="belly"></div>
            <div class="wing l"></div><div class="wing r"></div>
            <div class="eye l"></div><div class="eye r"></div>
            <div class="cheek l"></div><div class="cheek r"></div>
            <div class="beak"></div>
            <div class="foot l"></div><div class="foot r"></div>
          </div>
        </div>

        <div class="penguin rev p6" style="animation-delay:-5.2s;">
          <div class="tracks" aria-hidden="true"></div>
          <div class="pbody">
            <div class="body"></div><div class="belly"></div>
            <div class="wing l"></div><div class="wing r"></div>
            <div class="eye l"></div><div class="eye r"></div>
            <div class="cheek l"></div><div class="cheek r"></div>
            <div class="beak"></div>
            <div class="foot l"></div><div class="foot r"></div>
          </div>
        </div>

        <!-- Snowflakes -->
        <div class="flake" style="left:6%;  animation-duration: 9.6s; animation-delay:-1.0s; opacity:.65;"></div>
        <div class="flake" style="left:14%; animation-duration: 8.8s; animation-delay:-2.8s; opacity:.85;"></div>
        <div class="flake" style="left:22%; animation-duration: 9.2s; animation-delay:-5.2s; opacity:.75;"></div>
        <div class="flake" style="left:31%; animation-duration: 10.4s; animation-delay:-3.4s; opacity:.60;"></div>
        <div class="flake" style="left:39%; animation-duration: 9.0s; animation-delay:-6.0s; opacity:.78;"></div>
        <div class="flake" style="left:47%; animation-duration: 10.2s; animation-delay:-4.1s; opacity:.70;"></div>
        <div class="flake" style="left:56%; animation-duration: 8.6s; animation-delay:-2.1s; opacity:.82;"></div>
        <div class="flake" style="left:64%; animation-duration: 11.0s; animation-delay:-7.3s; opacity:.62;"></div>
        <div class="flake" style="left:72%; animation-duration: 9.4s; animation-delay:-3.0s; opacity:.74;"></div>
        <div class="flake" style="left:81%; animation-duration: 9.8s; animation-delay:-5.9s; opacity:.68;"></div>
        <div class="flake" style="left:89%; animation-duration: 8.7s; animation-delay:-1.7s; opacity:.86;"></div>
        <div class="flake" style="left:95%; animation-duration: 10.8s; animation-delay:-6.6s; opacity:.64;"></div>

        <div class="snow" aria-hidden="true"></div>
      </div>
    </div>
  </foreignObject>
</svg>

---
uid: "contribution/tunnel-game"
uid-meta: "contribution/tunnel-game-meta"
uid-files: "contribution/tunnel-game-files"
title: "Tunnel Game"
image: "TunnelGame.jpg"
contribution: "true"
---

You can control the aircraft, but you cannot hit the border. This is a kind of a game, made specially for stereoscopic awesomeness effect used with CIANT verticalizer.

The good thing is to create cylinders along the path by taking LookAt transform matrix on a series of points on B-Spline and apply them in Vertex shader. It's simple and works great. Bump mapping is just for an effect. The long light should show 3rd dimension in stereo, to lead an eye.

**BUG:** It takes some time to settle in, so first like 5 minutes you see only an aeroplane. But than, wait for it, a tunnel appears. The main purpose of this application was to make it in 2 days and it was, so don't say the code is not really clean and debugged :) I know.


btw, I need a job. Almost all the time nothing much to do. If you have something, tell me. 

martin@probenesov.cz
<http://martinzrcek.cz/en/>
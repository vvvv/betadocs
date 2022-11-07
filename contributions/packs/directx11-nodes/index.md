---
uid: "contribution/directx11-nodes"
uid-meta: "contribution/directx11-nodes-meta"
comments: 
 items: 
  - uid: "98981"
  - uid: "98982"
  - uid: "98986"
  - uid: "98987"
  - uid: "98988"
  - uid: "98994"
  - uid: "98996"
  - uid: "98997"
  - uid: "98998"
  - uid: "99002"
  - uid: "99003"
  - uid: "99004"
  - uid: "99007"
  - uid: "99008"
  - uid: "99026"
  - uid: "99071"
  - uid: "99079"
  - uid: "99112"
  - uid: "99115"
  - uid: "99246"
  - uid: "99269"
  - uid: "99280"
  - uid: "99422"
  - uid: "99480"
  - uid: "99495"
  - uid: "99574"
  - uid: "99576"
  - uid: "99678"
  - uid: "99706"
  - uid: "99732"
  - uid: "99752"
  - uid: "100337"
  - uid: "100338"
  - uid: "100343"
  - uid: "100350"
  - uid: "101509"
  - uid: "101514"
  - uid: "101678"
  - uid: "101752"
  - uid: "103370"
  - uid: "103393"
  - uid: "103916"
  - uid: "103918"
  - uid: "103934"
  - uid: "104125"
  - uid: "104303"
  - uid: "104859"
  - uid: "109553"
  - uid: "109868"
  - uid: "109905"
  - uid: "110632"
  - uid: "110641"
  - uid: "110647"
  - uid: "110713"
  - uid: "110750"
  - uid: "110780"
  - uid: "110782"
  - uid: "110783"
  - uid: "110785"
  - uid: "112897"
  - uid: "113075"
  - uid: "155659"
  - uid: "162428"
  - uid: "168248"
  - uid: "168253"
  - uid: "170221"
  - uid: "171762"
  - uid: "172287"
  - uid: "172395"
  - uid: "174156"
  - uid: "174388"
  - uid: "193699"
  - uid: "193763"
  - uid: "209552"
  - uid: "209553"
  - uid: "211673"
  - uid: "211675"
  - uid: "212355"
  - uid: "226502"
  - uid: "228299"
  - uid: "228313"
  - uid: "235068"
  - uid: "235073"
  - uid: "235160"
  - uid: "242709"
  - uid: "245423"
  - uid: "245473"
  - uid: "245528"
  - uid: "273060"
  - uid: "273895"
  - uid: "274255"
  - uid: "274523"
  - uid: "274530"
  - uid: "274531"
  - uid: "274579"
  - uid: "274701"
  - uid: "274704"
  - uid: "274760"
  - uid: "274815"
  - uid: "274825"
  - uid: "274830"
  - uid: "274831"
  - uid: "274851"
uid-files: "contribution/directx11-nodes-files"
title: "DirectX11 Nodes [dx11]"
image: "DX_org_2012.12.16-13.36.40.png"
contribution: "true"
---

DirectX11 rendering for vvvv (update 1.3)

See changes here: [directx11-1.3-update](/blog/directx11-1.3-update)

1.3.1 :
* Adds a small bug fix in case two group or enabled layers are stacked (exception would prevent rest of the groups to process)
* Adds a small issue if texture FX is in a disabled patch, sometimes would not resume.
* TextureFX that can use "wantmips" now do so (Edge, Blur, BlurDirectional, BlurGlow, BlurPerfector, DistortFlow, DropShadow, UnsharpMask) . They are all faster in that scenario.

General Changelog here : 
https://github.com/mrvux/dx11-vvvv/blob/master/CHANGELOG.md

Requires vvvv beta33.7 or newer.

Install Guide:
* Download relevant version
* Copy folder into vvvv directory, like you would do for addonpack or any other pack.

Submit bugs:
https://github.com/mrvux/dx11-vvvv/issues

Support development:
* Patreon : <http://www.patreon.com/mrvux>
* Private invoice (EU registered company) : contact me

Many thanks to people who are currently supporting development :

* Meso
* Wirmachenbunt
* Microdee
* Irwin Quemener - CloneProduction
* Intolight
* Ivan Kabalin
* Daniel Huber
* m4d
* Chris Plant
* Kyle McLean
* Andres
* Lev Panov
* Natan Sinigaglia
* Antokhio
* Andres
* Paul
* Jonas Häutle


---
uid: cecba36f-eba5-435b-b77e-2f466654c25c
---

#  The new thesis: high-resolution export with vvvv
It is the purpose of this thesis to develop a method that allows vvvv to export the generated graphics without any restriction of the image size. Because only resolution independent vector objects are used to generate images, there are no quality losses when enlarging. This fact is the key element needed to export very large images with vvvv. Due to hard- and software restrictions it is inevitable to split a file into multiple parts prior to exporting it. How this can be done and the resulting vvvv-patch are discussed in detail.  

The used method produces a certain number of images that have to be combined to create one big single image. This is not possible with vvvv, due to the limited export size. Because of this, another program has to be created to stitch the images together. Despite some extensive research, no suitable tool could be found for this task. A program had to be developed from scratch, it will also be discussed in this thesis. It is able to combine any number of images into one big image.  

[http://diploma.ampop.net]  

#  .generativvvve.
A book filled with generated images and a thesis (available only in german) about programmed design and art.  

[http://diploma.ampop.net]  

##  abstract: thesis
My thesis has the intention to extend the possibilities of the designer and to increase the quality and efficiency of his work.   
Because the term “generative design” is heavily influenced by the „programmed art“ movement and so some historical examples for programmed graphics, the techniques used for their creation are explained. This leads to the conclusion, that the creation of generative design demands another approach as the one common to designers.  
A basic understanding of mathematics and the use of a programming language are required, as well as the skill of expressing visual ideas in a way a computer can process.  
The well-established methods are all text-based languages and do not suit well the needs of visually thinking designers.  
This leads to the introduction of a graphical programming environment, which satisfies all demands of generative design. In addition, the discussed environment “vvvv” offers many functions to accelerate the handling of generated designs. These prerequisites ease the use of generative design-tools, even for those who never used a programming language.  

[http://diploma.ampop.net]  

##  intoduction to the book
Graphic design is the most prevalent form of all the arts. It fulfills personal needs as well as the needs of society and embraces both economic and ergonomic concepts; it is connected to numerous other disciplines including art, architecture and literature. Graphic design is produced in such volume that it covers most of our urban spaces and nearly every object we encounter in our everyday life. And still the designer’s profession and his way of life has not changed much since the early 1930s.  

Until the Second World War, graphic design was for the most part a commercial art practiced by printers and typesetters and rarely seen as an opportunity to implement ideas in a creative way. This was very unlike the experimental approach of the Bauhaus members, with their influences from cubism and constructivism. Their movement was driven by the demands of commerce, but fueled by the idea of eliminating the economic hardship caused by the Depression.  

Designers like Lester Beall and Paul Rand then combined this more art-like approach to graphic design with the purely commercial graphic design that the American economy demanded. This helped to inaugurate a new visual language that would revolutionize the role of design worldwide and until today.  

The relationships between art and design, between design and aesthetics, and between aesthetics and experience are the central topics of this emancipated design, as are the role of intuition and ideas, the balance between form and function and, maybe most importantly, the universal language of geometry and typography.  

To show how these ideas can be directly applied to the process of design creation, “.generativvvve.” contains a selection of 64 computer-generated images which were chosen from 128 originally created. Because the images were not created by the designer himself, but by a computer program written by the designer, the central question is whether a computer is capable of creating appealing design on its own, or whether the principles of aesthetics can only be conceived by humans or other intelligent forms of life.  

For each of the six chapters in “.generativvvve.”, a little program was produced. Each program is capable of producing a virtually unlimited number of images, and each image is unique, yet similar to the others. This is caused by a random or planned variation of the program’s input parameters. The designer defines behavioral rules, including their limits, and thus can, by carefully constructing this rulebook, achieve the desired result.   

The basic idea was to incorporate the ideas emphasized in the work of Paul Rand (“My interest has always been in restating the validity of those ideas, which, by and large, have guided artists since the time of Polyclitus.”) in the process of Generative Design by implementing the principles of aesthetics, form and function in a higher layer of the design process, outside of the designer’s brain.  
Therefore, Rand’s modernist ideology is somehow present in all the images printed in “.generativvvve.” , and even if the human mind steps aside and instructs the machine to make graphic designs on its own, the universal demands of aesthetics remain unchanged.  

Define the rules and give orders, then leave it to the machine to carry them out before you select the best design(s) for your purpose.   

[http://diploma.ampop.net]  

#  Everything changed
I had to change a few things, so all the prior work presented is pretty outdated, but can still be found here: [ampop_diploma_old](TODO INTERNALLINK:ampop_diploma_old)  
And maybe sometime I'll pick up my old direction and continue the creation of the vvvv print manual.
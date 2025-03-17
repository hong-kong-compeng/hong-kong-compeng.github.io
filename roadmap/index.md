---
title: Our suggested roadmap to study about compilers
---

Meetup notes

General
Our WhatsApp community: https://chat.whatsapp.com/JDzJRWVmlZyE5AbsB2jb88
If you are joining from this link, mention that you are not a bot "Hi, this is YOUR_NAME, I found a link on a website. I am a human!"


28 Aug 2024
Ocaml compiler github repo: https://github.com/ocaml/ocaml

The main book for general guidance: https://www.cs.princeton.edu/~appel/modern/ml/

aarch32 assembly code generation book: https://keleshev.com/compiling-to-assembly-from-scratch/

Ocaml study materials:
Textbook https://dev.realworldocaml.org/
Video lectures https://www.youtube.com/@MichaelRyanClarkson/playlists


Parser generator library for Ocaml we gonna use for our implementations: https://gallium.inria.fr/~fpottier/menhir/

Tiger language specification - https://www.cs.columbia.edu/~sedwards/classes/2002/w4115/tiger.pdf

Expectations for week 2:

Real World Ocaml book: learn syntax, and environment (ADT, modules)
Modern compiler implementation in ML book: Introduction (Chapter 1) + exercises




4 Sept 2024


open Base
open Stdio

type id = string

type binop = Plus | Minus | Times | Div

type stm = Compound of stm * stm
     	| Assign of id * exp
     	| Print of exp list
and exp = Id of id
     	| Num of int
     	| Op of exp * binop * exp
     	| Eseq of stm * exp

(* Your code goes here >>> *)

(* Example AST representation in OCaml *)
let example_program = Compound(
  Assign("a", Op(Num 5, Plus, Num 3)),
  Compound(
	Assign("b",
  	Eseq(
    	Print [Id "a"; Op(Id "a", Minus, Num 1)],
    	Op(Num 10, Times, Id "a"))),
	Print [Id "b"]))



Ocaml init file for homedir


~/.ocamlinit

#require "core.top";;
#require "ppx_jane";;


(*I am not sure I want to load Base module everytime I access utop environment*)
(*open Base;;*)


25 September
—-------
2 October

Nice intro article to learn about building lexers and parsers in Ocaml
https://dev.realworldocaml.org/parsing-with-ocamllex-and-menhir.html








Roadmap

1 week: Setup Ocaml. 1 chapter RWO. Play around Ocaml.
2 week: 


Read frist 6 chapters of Real world Ocaml to get familiar with syntax and language contstructions.

Read chapter 1 of THE BOOK, try to use ocaml to do exercise 1 from the book

Read chapter 19 of Real world ocaml to learn about ocamllex and menhir and how to build json lexer and parser with them

Read chapter 2 and 3 from THE BOOK to get theoretical knowledge about lexers and parsers and implement XML lexer and parser to practice ocamllex and menhir more

Switch to implementing Tiger language lexer and parser (TODO: add a link to the book)



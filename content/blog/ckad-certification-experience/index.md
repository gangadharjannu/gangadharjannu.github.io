---
title: My CKAD certification experience
date: "2023-10-15T11:25:00.000Z"
description: "Recently I become CKAD certified and would like to share my experience"
---

Recently I become CKAD certified and would like to share my experience

## Sections

1. What
2. Why
3. Personal experience
4. Syllabus
   1. Topics with percentage
5. Preparation
   1. Personal preparation
6. Tips & suggestions
   1. User experience of exam
   2. Time management
   3. Tracking progress

## What ?

Certified Kubernetes Application Developer

## why ?

For engineers

It proves that you invested your time for doing certification.
If you want to switch careers, this is one of the way which shows you are one among few.

## Personal experience

To understand more about containerization and speak better with DevOps.

Also I strongly believe more apps will be containerized which means more scope for this kind of work.

## Syllabus

| Percentage | Topic                                               |
| ---------- | --------------------------------------------------- |
| 20%        | Application Design and Build                        |
| 20%        | Application Deployment                              |
| 15%        | Application Observability and Maintenance           |
| 25%        | Application Environment, Configuration and Security |
| 20%        | Services and Networking                             |

## Preparation

1. https://github.com/dgkanatsios/CKAD-exercises with `kind` or `minikube` or `docker desktop` was useful.
2. [KodeKloud](https://kodekloud.com/courses/certified-kubernetes-application-developer-ckad/) course and labs was super useful.
3. Practice practice practice!
4. Work experience helped me a lot.

Take any of your old application which you used `docker` to build the image and `docker` or `docker compose` to deploy it then try to convert that to `Kubernetes`.

Environment variables will go either in `secrets` or `configmaps` depending on sensitivity of data.

Storage volumes goes to `PV` or `PVC`

You need a `service` to interact with a pod and also with other services (lets ignore port-forwarding for the sake of learning).

By doing this exercise, you will learn containerizing your application.

## Exam details

Online exam, proctored, performance-based test that consists of a set of performance-based tasks (problems) to be solved in a command line.

Duration **2 hours**.

2 attempts (per exam registration) to an exam simulator, provided by [Killer.sh](killer.sh).

As of now the exam is based on `Kubernetes` `v1.28`. It changes whenever there is a new version.

## Exam tips

Practice using `Vi`, `vim`, `Nano` and also learn their shortcuts.

How to `copy` and `paste` within terminal and outside terminal and also key binding difference in windows and mac.

Use [killer.sh](killer.sh) for practice.

**My suggestion to track progress of exam:**

Open a new tab in terminal
open a new file with nano or vi or vim
Quickly read the question, understand the topic it aims, think about solution in less than one minute, short summary of solution in your words (one or two lines) and mark it as easy, medium or difficult as per your knowledge and understanding

It works like index

And when you are done working on problem (not necessarily means it solved), mark the question with your result like (solved, needs checking, difficult, check later...)

Don't spend too much time early in your exam.

First finish all the known/easier ones and then do the medium then do the complex.

If you do the complex one first, your mind may gets disturbed and you won't be able to concentrate on other questions.

**Final suggestions:**

Prepare based on your experience, skills, knowledge and understanding

Attempt with confidence

All the best!

## References

[curriculum](https://github.com/cncf/curriculum)  
[tips](https://docs.linuxfoundation.org/tc-docs/certification/tips-cka-and-ckad)  
[faq](https://docs.linuxfoundation.org/tc-docs/certification/faq-cka-ckad-cks)

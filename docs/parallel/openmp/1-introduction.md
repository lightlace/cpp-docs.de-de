---
title: 1. Einführung | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: c42e72bc-0e31-4b1c-b670-cd82673c0c5a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 883af9cb48a0fb13dbb9a758d6f8174096d4c0c3
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33685839"
---
# <a name="1-introduction"></a>1. Einführung
Dieses Dokument gibt eine Auflistung von Compiler-Direktiven, Bibliotheksfunktionen und Umgebungsvariablen, die zum Angeben von shared Memory-Parallelität in C und C++-Programmen verwendet werden können. In diesem Dokument beschriebene Funktionalität wird zusammenfassend als bezeichnet den *OpenMP C/C++-Anwendung die API (Anwendungsprogrammierschnittstelle)*. Das Ziel dieser Spezifikation ist, um ein Modell bereitzustellen, zur parallelen Programmierung, die ein Programm über das shared Memory-Architekturen von unterschiedlichen Anbietern portabel sein können. OpenMP-C-/C++-API wird von Compilern von zahlreichen Anbietern unterstützt werden. Weitere Informationen zu OpenMP, einschließlich der *OpenMP Fortran Anwendungsprogrammierschnittstelle*, finden Sie unter der folgenden Website:  
  
 [http://www.openmp.org](http://www.openmp.org)  
  
 Die Direktiven, Bibliotheksfunktionen und Umgebungsvariablen, die in diesem Dokument definierte können Benutzer zum Erstellen und verwalten parallele Programme zugleich Portabilität. Die Direktiven erweitern C und C++ sequenzielle Programmierungsmodells mit einzelnen Programm mehrerer-(SPMD)-Konstrukte, Arbeitsteilungskonstrukte und Konstrukte für die Synchronisierung, und sie bieten Unterstützung für die gemeinsame Nutzung und Privatisierung Datenmenge. Compiler, die OpenMP-C- und C++-API unterstützen, werden eine Befehlszeilenoption für den Compiler enthalten, die aktiviert und ermöglicht die Darstellung aller OpenMP Compilerdirektiven.
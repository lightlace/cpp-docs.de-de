---
title: "1. Einführung | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: c42e72bc-0e31-4b1c-b670-cd82673c0c5a
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f850e236ebfd056da93700df06ec830e5a573284
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="1-introduction"></a>1. Einführung
Dieses Dokument gibt eine Auflistung von Compiler-Direktiven, Bibliotheksfunktionen und Umgebungsvariablen, die zum Angeben von shared Memory-Parallelität in C und C++-Programmen verwendet werden können. In diesem Dokument beschriebene Funktionalität wird zusammenfassend als bezeichnet den *OpenMP C/C++-Anwendung die API (Anwendungsprogrammierschnittstelle)*. Das Ziel dieser Spezifikation ist, um ein Modell bereitzustellen, zur parallelen Programmierung, die ein Programm über das shared Memory-Architekturen von unterschiedlichen Anbietern portabel sein können. OpenMP-C-/C++-API wird von Compilern von zahlreichen Anbietern unterstützt werden. Weitere Informationen zu OpenMP, einschließlich der *OpenMP Fortran Anwendungsprogrammierschnittstelle*, finden Sie unter der folgenden Website:  
  
 [http://www.OpenMP.org](http://www.openmp.org)  
  
 Die Direktiven, Bibliotheksfunktionen und Umgebungsvariablen, die in diesem Dokument definierte können Benutzer zum Erstellen und verwalten parallele Programme zugleich Portabilität. Die Direktiven erweitern C und C++ sequenzielle Programmierungsmodells mit einzelnen Programm mehrerer-(SPMD)-Konstrukte, Arbeitsteilungskonstrukte und Konstrukte für die Synchronisierung, und sie bieten Unterstützung für die gemeinsame Nutzung und Privatisierung Datenmenge. Compiler, die OpenMP-C- und C++-API unterstützen, werden eine Befehlszeilenoption für den Compiler enthalten, die aktiviert und ermöglicht die Darstellung aller OpenMP Compilerdirektiven.
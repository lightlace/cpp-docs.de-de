---
title: "Initialisiererlisten | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Initialisiererlisten"
ms.assetid: b3e53442-9809-4105-9226-ae845bd20cae
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# Initialisiererlisten
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Initialisierungslisten in Konstruktoren werden jetzt vor dem Basisklassenkonstruktor aufgerufen.  
  
## Hinweise  
 Vor der Version Visual C\+\+ 2005 wurde der Basisklassenkonstruktor beim Kompilieren mit Managed Extensions for C\+\+ vor der Initialisierungsliste aufgerufen.  Jetzt wird beim Kompilieren mit **\/clr** die Initialisierungsliste zuerst aufgerufen.  
  
## Siehe auch  
 [Allgemeine Sprachänderung](../dotnet/general-language-changes-cpp-cli.md)
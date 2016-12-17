---
title: "Initialisiererlisten"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Initialisiererlisten"
ms.assetid: b3e53442-9809-4105-9226-ae845bd20cae
caps.latest.revision: 4
caps.handback.revision: "4"
ms.author: "mblome"
manager: "ghogen"
---
# Initialisiererlisten
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Initialisierungslisten in Konstruktoren werden jetzt vor dem Basisklassenkonstruktor aufgerufen.  
  
## Hinweise  
 Vor der Version Visual C\+\+ 2005 wurde der Basisklassenkonstruktor beim Kompilieren mit Managed Extensions for C\+\+ vor der Initialisierungsliste aufgerufen.  Jetzt wird beim Kompilieren mit **\/clr** die Initialisierungsliste zuerst aufgerufen.  
  
## Siehe auch  
 [Allgemeine Sprachänderung](../dotnet/general-language-changes-cpp-cli.md)
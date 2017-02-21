---
title: "Vermeiden von Ausnahmen beim Herunterfahren der CLR, wenn mit /clr erstellte COM-Objekte verwendet werden | Microsoft Docs"
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
  - "/clr-Compileroption [C++], Ausnahmen beim Herunterfahren der CLR"
  - "/clr-Compileroption [C++], COM-Objekte"
  - "Ausnahmen beim Herunterfahren der CLR [C++]"
  - "Interop [C++], Ausnahmen beim Herunterfahren der CLR"
  - "Interoperabilität [C++], Ausnahmen beim Herunterfahren der CLR"
  - "Gemischte Assemblys [C++], Ausnahmen beim Herunterfahren der CLR"
ms.assetid: 41249d83-4b51-4e46-866f-27f475f2498c
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# Vermeiden von Ausnahmen beim Herunterfahren der CLR, wenn mit /clr erstellte COM-Objekte verwendet werden
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Sobald die Common Language Runtime \(CLR\) in den Modus für das Herunterfahren wechselt, wird der Zugriff systemeigener Funktionen auf CLR\-Dienste eingeschränkt.  Wenn versucht wird, für ein COM\-Objekt, das mit **\/clr** kompiliert wurde, Release aufzurufen, geht die CLR in systemeigenen Code über und wechselt anschließend zurück in verwalteten Code, um den IUnknown::Release\-Aufruf zu verarbeiten \(der in verwaltetem Code definiert ist\).  Die CLR verhindert den Rückruf in verwalteten Code, wenn sie sich im Modus für das Herunterfahren befindet.  
  
 Um dieses Problem zu lösen, sollten Sie sicherstellen, dass von Release\-Methoden aufgerufene Destruktoren nur systemeigenen Code enthalten.  
  
## Siehe auch  
 [Gemischte \(systemeigene und verwaltete\) Assemblys](../dotnet/mixed-native-and-managed-assemblies.md)
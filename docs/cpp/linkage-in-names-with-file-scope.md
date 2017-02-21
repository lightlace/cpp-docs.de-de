---
title: "Verkn&#252;pfung in Namen mit Dateibereich | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Deklarationen [C++], Extern"
  - "Externe Verknüpfung, Bereich der Verknüpfungsregeln"
  - "Dateibereich [C++]"
  - "Verknüpfung [C++], Bereich der Verknüpfungsregeln"
  - "Namen [C++], Bereich der Verknüpfungsregeln"
  - "Bereich [C++], Verknüpfungsregeln"
  - "static-Modifizierer, Dateibereich"
  - "Statistischen Namen und Dateibereich"
  - "Statische Variablen, Externe Deklarationen"
ms.assetid: 38d3fa5e-1861-466e-a590-84b86f7b184e
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Verkn&#252;pfung in Namen mit Dateibereich
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die folgenden Verknüpfungsregeln gelten für Namen \(außer `typedef` und Enumeratornamen\) mit dem Dateibereich:  
  
-   Wenn ein Name explizit als **static** deklariert wird, verfügt er über interne Verknüpfung und identifiziert ein Programmelement in seiner eigenen Übersetzungseinheit.  
  
-   Enumeratornamen und `typedef`\-Namen haben keine Verknüpfung.  
  
-   Alle anderen Namen mit Dateigültigkeitsbereich haben externe Verknüpfung.  
  
 **Microsoft\-spezifisch**  
  
-   Wenn ein Funktionsname mit Dateigültigkeitsbereich explizit als **inline** deklariert wird, erfolgt die Verknüpfung extern, wenn die Funktion instanziiert wird oder auf ihre Adresse verwiesen wird.  Daher kann eine Funktion mit Dateigültigkeitsbereich entweder eine interne oder eine externe Verknüpfung besitzen.  
  
 **Ende Microsoft\-spezifisch**  
  
 In folgenden Fällen verfügt eine Klasse über interne Verknüpfung:  
  
-   Sie verwendet keine C\+\+\-Funktionalität \(z. B. Zugriffssteuerung, Memberfunktionen, Konstruktoren, Destruktoren usw.\).  
  
-   Sie wird nicht in der Deklaration eines anderen Namens mit externer Verknüpfung verwendet.  Diese Einschränkung bedeutet, dass Objekte vom Klassentyp, die an Funktionen mit externer Verknüpfung übergeben werden, eine externe Verknüpfung der Klasse verursachen.  
  
## Siehe auch  
 [Programm und Verknüpfung](../cpp/program-and-linkage-cpp.md)
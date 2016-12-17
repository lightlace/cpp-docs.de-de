---
title: "Verkn&#252;pfung in Namen mit Dateibereich"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
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
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
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
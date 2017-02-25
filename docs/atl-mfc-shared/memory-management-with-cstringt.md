---
title: "Memory Management with CStringT | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CStringT"
  - "ATL::CStringT"
  - "ATL.CStringT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CFixedStringT class, description of"
  - "CString objects, Speicherverwaltung"
  - "CStringT class, Speicherverwaltung"
  - "IAtlStringMgr class, Verwenden"
  - "Speicher [C++], Verwendung"
  - "Zeichenfolgen [C++], custom memory management"
  - "Zeichenfolgen [C++], Speicherverwaltung"
ms.assetid: 88b8342d-19b5-48c4-9cf6-e4c44cece21e
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Memory Management with CStringT
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[CStringT](../atl-mfc-shared/reference/cstringt-class.md)\-Klasse ist eine Vorlagenklasse, die verwendet wird, um zu bearbeiten Zeichenfolgen variabler Länge.  Der Speicher, um diese Zeichenfolgen angehalten wird durch ein Zeichenfolgenmanagerobjekt reserviert und freigegeben, das mit jeder Instanz von `CStringT` zugeordnet ist.  MFC und ATL stellt die standardmäßige Instanziierungen von `CStringT`, aufgerufen `CString`, `CStringA` und `CStringW`, die Zeichenfolgen von verschiedenen Zeichentypen bearbeiten.  Diese Zeichentypen sind vom Typ **TCHAR**, `char` und `wchar_t`, bzw.  Diese Standardeinstellung Zeichenfolgentypen verwenden einen Zeichenfolgenmanager, der vom Prozessheap \(in ATL\) oder dem CRT\-Heap Speicher belegt \(in MFC\).  Für typische Anwendungen ist dies Speicherbelegungsschema ausreichend.  Für Code, der intensive Verwendung von Zeichenfolgen ausführen \(oder Multithreadcode\), das die standardmäßige Speicher\-Manager möglicherweise nicht optimal ausführen.  In diesem Thema wird beschrieben, wie das standardmäßige Speicherverwaltungsverhalten von `CStringT` überschrieben und die Belegungsfunktionen erstellt, die speziell für die Aufgabe der Blatt optimiert werden.  
  
-   [Implementierung eines benutzerdefinierten Zeichenfolgen\-Managers \(grundlegende Methode\)](../atl-mfc-shared/implementation-of-a-custom-string-manager-basic-method.md)  
  
-   [Vermeiden von Heap\-Konflikts](../atl-mfc-shared/avoidance-of-heap-contention.md)  
  
-   [Implementierung eines benutzerdefinierten Zeichenfolgen\-Managers erweiterte \(Methode\)](../atl-mfc-shared/implementation-of-a-custom-string-manager-advanced-method.md)  
  
-   [CFixedStringT: Ein Beispiel eines benutzerdefinierten Zeichenfolgen\-Managers](../atl-mfc-shared/cfixedstringt-example-of-a-custom-string-manager.md)  
  
## Siehe auch  
 [CustomString\-Beispiel](../top/visual-cpp-samples.md)
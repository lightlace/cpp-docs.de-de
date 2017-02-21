---
title: "Dispatchzuordnungen | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.mfc.macros.maps"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Dispatchzuordnungsmakros"
  - "Dispatchzuordnungen"
  - "Dispatchzuordnung. Makros"
ms.assetid: bef9d08b-ad35-4c3a-99d8-04150c7c04e2
caps.latest.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 15
---
# Dispatchzuordnungen
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

OLE\-Automatisierung stellt Methoden, Methoden aufzurufen und auf Eigenschaften über Anwendungen zugreifen.  Der Mechanismus, der von der Microsoft Foundation Class\-Bibliothek für das Routing Anforderungen dieser angegeben wird, ist die "Dispatchzuordnung,", die die internen und externen Namen der Objektfunktionen und \- eigenschaften festlegen sowie die Datentypen der Eigenschaften selbst und die Funktionsargumente.  
  
### Dispatchzuordnungen  
  
|||  
|-|-|  
|[DECLARE\_DISPATCH\_MAP](../Topic/DECLARE_DISPATCH_MAP.md)|Deklariert, dass eine Dispatchzuordnung verwendet wird, um die Methoden und Eigenschaften einer Klasse verfügbar zu machen \(muss in der Klassendeklaration verwendet werden\).|  
|[BEGIN\_DISPATCH\_MAP](../Topic/BEGIN_DISPATCH_MAP.md)|Startet die Definition einer Dispatchzuordnung.|  
|[END\_DISPATCH\_MAP](../Topic/END_DISPATCH_MAP.md)|Beendet die Definition einer Dispatchzuordnung.|  
|[DISP\_FUNCTION](../Topic/DISP_FUNCTION.md)|Wird in einer Dispatchzuordnung, um eine OLE\-Automatisierungs\-Funktion zu definieren.|  
|[DISP\_PROPERTY](../Topic/DISP_PROPERTY.md)|Definiert eine OLE\-Automatisierungs\-Eigenschaft.|  
|[DISP\_PROPERTY\_EX](../Topic/DISP_PROPERTY_EX.md)|Definiert eine OLE\-Automatisierungs\-Eigenschaft und nennt das Ausschließen des set\-Indexers und festzulegen Funktionen.|  
|[DISP\_PROPERTY\_NOTIFY](../Topic/DISP_PROPERTY_NOTIFY.md)|Definiert eine OLE\-Automatisierungs\-Eigenschaft mit Benachrichtigung.|  
|[DISP\_PROPERTY\_PARAM](../Topic/DISP_PROPERTY_PARAM.md)|Definiert eine OLE\-Automatisierungs\-Eigenschaft, die Parameter akzeptiert und durch den Abruf und festzulegen Funktionen benennt.|  
|[DISP\_DEFVALUE](../Topic/DISP_DEFVALUE.md)|Macht eine bereits bestehende Eigenschaft den Standardwert ein Objekt.|  
  
## Siehe auch  
 [MFC\-Makros, globale Funktionen und globale Variablen](../../mfc/reference/mfc-macros-and-globals.md)
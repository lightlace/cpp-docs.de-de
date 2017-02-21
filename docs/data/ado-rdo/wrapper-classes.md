---
title: "Wrapperklassen | Microsoft Docs"
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
  - "ActiveX-Steuerelemente [C++], Wrapperklassen"
  - "Datenbindung [C++], ActiveX-Steuerelemente"
  - "Wrapperklassen [C++], ActiveX-Steuerelemente"
ms.assetid: ebbc17b9-cc1b-4c29-afa9-da7f9511876e
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Wrapperklassen
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Beim [Einfügen eines Steuerelements](../../data/ado-rdo/inserting-the-control-into-a-visual-cpp-application.md) in ein Visual C\+\+\-Projekt werden nicht automatisch Wrapperklassen für das Steuerelement eingefügt.  Wenn Sie jedoch das [Verhalten des Steuerelements ändern](../../data/ado-rdo/modifying-a-control-s-run-time-behavior.md) möchten, können Sie eine Wrapperklasse für das Steuerelement schreiben.  Je nachdem, auf welche Weise das Steuerelement programmgesteuert angepasst werden soll, können Sie eine oder mehrere Wrapperklassen für das Steuerelement schreiben.  
  
 Für jede der Co\-Klassen in der Typbibliothek \(**.tlb**\) des Steuerelements ist eine Wrapperklasse verfügbar.  Der Name der Wrapperklasse sollte dem Namen des dazugehörigen Steuerelements mit vorangestelltem C entsprechen.  
  
 Weitere Informationen über die Funktionen von Wrapperklassen finden Sie unter dem Objektmodell, das sich auf die Basistechnologie des jeweiligen Steuerelements bezieht.  
  
 Die Verwendung von [CWnd::GetDlgItem](../Topic/CWnd::GetDlgItem.md) setzt ebenfalls Wrapperklassen voraus, da der Rückgabewert in die Steuerelementklasse umgewandelt werden muss.  Beispiel:  
  
```  
CDBList* pDBList = 0;  
pDBList = static_cast<CDBList*>(GetDlgItem(IDC_DBLIST));  
```  
  
 Anhand der generierten IDL\-Datei lässt sich ermitteln, welche Eigenschaften, Methoden und Ereignisse von einem Steuerelement verfügbar gemacht werden. Außerdem sind die Deklarationen für Methoden\- und Accessorfunktionen direkt ersichtlich.  Zusätzliche Informationen erhalten Sie über das Steuerelement selbst im [OLE\/COM\-Objektkatalog](../../data/ado-rdo/using-the-ole-com-object-viewer.md).  
  
## Siehe auch  
 [Verwenden von ActiveX\-Steuerelementen](../../data/ado-rdo/using-activex-controls.md)   
 [Ändern des Laufzeitverhaltens eines Steuerelements](../../data/ado-rdo/modifying-a-control-s-run-time-behavior.md)
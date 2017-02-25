---
title: "Standardroutinen zur Pr&#252;fung der Dialogfelddaten | Microsoft Docs"
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
  - "Standarddialog, Datenvalidierungsroutine"
ms.assetid: 44dbc222-a897-4949-925e-7660e8964ccd
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# Standardroutinen zur Pr&#252;fung der Dialogfelddaten
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Dieses Thema führt die Standarddialogfelddatenvalidierungs\- Routinen \(DDV\)\- auf, die für Dialogfeldkontrollen des Common MFC verwendet werden.  
  
> [!NOTE]
>  Die Standarddialogdatenaustauschroutinen werden in der Headerdatei afxdd\_.h. definiert.  Allerdings sollten Anwendungen afxwin.h enthalten.  
  
### DDV\-Funktionen  
  
|||  
|-|-|  
|[DDV\_MaxChars](../Topic/DDV_MaxChars.md)|Überprüft die Anzahl von Zeichen in einem angegebenen Steuerelementwert überschreitet kein bestimmtes Maximalwert.|  
|[DDV\_MinMaxByte](../Topic/DDV_MinMaxByte.md)|Überprüft einen angegebenen Steuerelementwert überschreitet keinen angegebenen **BYTE** Bereich.|  
|[DDV\_MinMaxDateTime](../Topic/DDV_MinMaxDateTime.md)|Überprüft einen angegebenen Steuerelementwert überschreitet keinen jeweiligen Zeitraum.|  
|[DDV\_MinMaxDouble](../Topic/DDV_MinMaxDouble.md)|Überprüft einen angegebenen Steuerelementwert überschreitet keinen angegebenen **double** Bereich.|  
|[DDV\_MinMaxDWord](../Topic/DDV_MinMaxDWord.md)|Überprüft einen angegebenen Steuerelementwert überschreitet keinen angegebenen **DWORD** Bereich.|  
|[DDV\_MinMaxFloat](../Topic/DDV_MinMaxFloat.md)|Überprüft einen angegebenen Steuerelementwert überschreitet keinen angegebenen **float** Bereich.|  
|[DDV\_MinMaxInt](../Topic/DDV_MinMaxInt.md)|Überprüft einen angegebenen Steuerelementwert überschreitet keinen angegebenen **int** Bereich.|  
|[DDV\_MinMaxLong](../Topic/DDV_MinMaxLong.md)|Überprüft einen angegebenen Steuerelementwert überschreitet keinen angegebenen **long** Bereich.|  
|[DDV\_MinMaxLongLong](../Topic/DDV_MinMaxLongLong.md)|Überprüft einen angegebenen Steuerelementwert überschreitet keinen angegebenen **LONGLONG** Bereich.|  
|[DDV\_MinMaxMonth](../Topic/DDV_MinMaxMonth.md)|Überprüft einen angegebenen Steuerelementwert überschreitet keinen angegebenen Datumsbereich.|  
|[DDV\_MinMaxShort](../Topic/DDV_MinMaxShort.md)|Überprüft einen angegebenen Steuerelementwert überschreitet keinen angegebenen **short** Bereich.|  
|[DDV\_MinMaxSlider](../Topic/DDV_MinMaxSlider.md)|Überprüft Fälle eines angegebenen Schieberegler\-Steuerelement\-Werts innerhalb des angegebenen Bereichs.|  
|[DDV\_MinMaxUInt](../Topic/DDV_MinMaxUInt.md)|Überprüft einen angegebenen Steuerelementwert überschreitet keinen angegebenen **UINT** Bereich.|  
|[DDV\_MinMaxULongLong](../Topic/DDV_MinMaxULongLong.md)|Überprüft einen angegebenen Steuerelementwert überschreitet keinen angegebenen **ULONGLONG** Bereich.|  
  
## Siehe auch  
 [Standarddialogdatenaustausch\-Routinen](../../mfc/reference/standard-dialog-data-exchange-routines.md)   
 [MFC\-Makros, globale Funktionen und globale Variablen](../../mfc/reference/mfc-macros-and-globals.md)
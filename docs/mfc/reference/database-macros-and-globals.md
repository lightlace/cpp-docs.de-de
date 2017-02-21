---
title: "Datenbankmakros und globale Variablen | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.mfc.macros.data"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Datenbankenglobals [C++]"
  - "Datenbankmakros [C++]"
  - "Globale Datenbankfunktionen [C++]"
  - "Globale Funktionen [C++], Datenbankfunktionen"
  - "Makros [C++], MFC-Datenbank"
ms.assetid: 5b9b9e61-1cf9-4345-9f29-3807dd466488
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# Datenbankmakros und globale Variablen
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die Makros und globalen Werten, unten aufgeführten werden, gelten für ODBC\-basierte Datenbankanwendungen zu.  Sie werden nicht mit DAO\-basierten Anwendungen.  
  
 Vor MFC 4.2 haben die Makros `AFX_SQL_ASYNC` und `AFX_SQL_SYNC` asynchronen Operationen eine Gelegenheit, Zeit an andere Prozesse zu führen.  Ab MFC 4.2, wurde die Implementierung dieser Makros, da die MFC\-ODBC\- nur synchronen Operationen haben.  Makro\- `AFX_ODBC_CALL` war zu MFC 4.2 neu.  
  
### Datenbank\-Makros  
  
|||  
|-|-|  
|[AFX\_ODBC\_CALL](../Topic/AFX_ODBC_CALL.md)|Ruft eine ODBC\-API\-Funktion auf, die `SQL_STILL_EXECUTING` zurückgibt.  `AFX_ODBC_CALL` ruft überprüft die Funktion auf, wenn sie nicht mehr `SQL_STILL_EXECUTING` zurückgibt.|  
|[AFX\_SQL\_ASYNC](../Topic/AFX_SQL_ASYNC.md)|Aufrufen von `AFX_ODBC_CALL`.|  
|[AFX\_SQL\_SYNCHRONIZATION](../Topic/AFX_SQL_SYNC.md)|Ruft eine ODBC\-API\-Funktion auf, die nicht `SQL_STILL_EXECUTING` zurückgibt.|  
  
### Datenbank\-globale Werte  
  
|||  
|-|-|  
|[AfxGetHENV](../Topic/AfxGetHENV.md)|Ruft ein Handle für die ODBC\-Umgebung derzeit von MFC ab.  Sie können dieses Handle in direkten ODBC\-Aufrufen verwenden.|  
  
## Siehe auch  
 [MFC\-Makros, globale Funktionen und globale Variablen](../../mfc/reference/mfc-macros-and-globals.md)
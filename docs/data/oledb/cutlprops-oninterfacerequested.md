---
title: "CUtlProps::OnInterfaceRequested | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CUtlProps"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "OnInterfaceRequested-Methode"
ms.assetid: a5e1a879-cff3-4e01-b902-2249a152984f
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# CUtlProps::OnInterfaceRequested
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Handleersuchen um eine optionale Schnittstelle, wenn ein Consumer aufruft, eine Methode auf einer der Objekterstellung verbindet.  
  
## Syntax  
  
```  
  
      virtual HRESULT CUtlPropsBase::OnInterfaceRequested(  
   REFIID riid  
);  
```  
  
#### Parameter  
 `riid`  
 \[in\] die IID für die angeforderte Schnittstelle.  Ausführliche Informationen finden Sie in der Beschreibung des Parameters `riid` von `ICommand::Execute` in der *OLE* DB\-Programmierreferenz im *MDAC SDK*\(\).  
  
## Hinweise  
 **OnInterfaceRequested**  behandelt Consumerersuchen um eine optionale Schnittstelle, wenn ein Consumer eine Methode auf einer der Objekterstellungsschnittstellen aufruft \(wie **IDBCreateSession**, **IDBCreateCommand**, `IOpenRowset` oder `ICommand`\).  Er legt die entsprechende OLE DB\-Eigenschaft für die angeforderte Schnittstelle fest.  Wenn der Consumer **IID\_IRowsetLocate** anfordert, legt **OnInterfaceRequested** die Schnittstelle **DBPROP\_IRowsetLocate** fest.  Hiermit behält so den richtigen Zustand während der Rowseterstellung bei.  
  
 Diese Methode wird aufgerufen, wenn der Consumer **IOpenRowset::OpenRowset** oder `ICommand::Execute` aufrufen.  
  
 Wenn ein Consumer ein Objekt wird und um eine optionale Schnittstelle anfordert, sollte der Anbieter die Eigenschaft festlegen, die dieser Schnittstelle auf `VARIANT_TRUE` zugeordnet ist.  Um das eigenschaftenspezifische Verarbeitung zu ermöglichen, wird **OnInterfaceRequested**  aufgerufen bevor die **Ausführen** \-Methode des Anbieters aufgerufen wird.  Standardmäßig behandelt **OnInterfaceRequested**  die folgenden Schnittstellen:  
  
-   `IRowsetLocate`  
  
-   `IRowsetChange`  
  
-   `IRowsetUpdate`  
  
-   **IConnectionPointContainer**  
  
-   `IRowsetScroll`  
  
 Wenn Sie weitere Schnittstellen behandeln, überschreiben Sie diese Funktion in der Datenquelle, der Sitzung, in Befehl, oder in Funktionen Rowsetklasse, zu verarbeiten.  Die Überschreibung, sollte das normale festgelegte durchlaufen\/ruft Eigenschaftenschnittstellen ab, dass das Festlegen von Eigenschaften sicherzustellen, auch sämtliche verketteten Eigenschaften festlegen \(siehe [OnPropertyChanged](../../data/oledb/cutlprops-onpropertychanged.md)\).  
  
## Anforderungen  
 **Header:** atldb.h  
  
## Siehe auch  
 [CUtlProps\-Klasse](../../data/oledb/cutlprops-class.md)
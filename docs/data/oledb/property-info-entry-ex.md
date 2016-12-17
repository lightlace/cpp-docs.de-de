---
title: "PROPERTY_INFO_ENTRY_EX"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "PROPERTY_INFO_ENTRY_EX"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "PROPERTY_INFO_ENTRY_EX-Makro"
ms.assetid: af32dfcd-4c50-449d-af3b-48d21bd67a04
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# PROPERTY_INFO_ENTRY_EX
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Stellt eine bestimmte Eigenschaft in einem Eigenschaftensatz dar.  
  
## Syntax  
  
```  
  
PROPERTY_INFO_ENTRY_EX(  
dwPropID  
,  
vt  
,  
dwFlags  
,  
value  
,  
options  
)  
  
```  
  
#### Parameter  
 *dwPropID*  
 \[in\] Ein [DBPROPID](https://msdn.microsoft.com/en-us/library/ms723882.aspx)\-Wert, der in Verbindung mit dem GUID\-Eigenschaftensatz verwendet werden kann, um eine Eigenschaft zu identifizieren.  
  
 *vt*  
 \[in\] Die [VARTYPE](assetId:///317b911b-1805-402d-a9cb-159546bc88b4) dieses Eigenschaftseintrags.  
  
 `dwFlags`  
 \[in\] Ein [DBPROPFLAGS](https://msdn.microsoft.com/en-us/library/ms724342.aspx)\-Wert, der diesen Eigenschaftseintrag beschreibt.  
  
 *Wert*  
 \[in\] Der Eigenschaftswert von Typ `DWORD`.  
  
 `options`  
 Entweder **DBPROPOPTIONS\_REQUIRED** oder **DBPROPOPTIONS\_SETIFCHEAP**. In der Regel muss ein Anbieter `options` nicht festlegen, da dies vom Consumer festgelegt wird.  
  
## Hinweise  
 Mit diesem Makro können Sie den Wert der Eigenschaft des Typs `DWORD` sowie Optionen und Flags direkt angeben. Um lediglich einen in ATLDB.H definierten Standardwert für eine Eigenschaft festzulegen, verwenden Sie [PROPERTY\_INFO\_ENTRY](../../data/oledb/property-info-entry.md). Um einen Wert Ihrer Wahl für eine Eigenschaft festzulegen, verwenden Sie [PROPERTY\_INFO\_ENTRY\_VALUE](../../data/oledb/property-info-entry-value.md).  
  
## Beispiel  
 Siehe [BEGIN\_PROPSET\_MAP](../../data/oledb/begin-propset-map.md).  
  
## Anforderungen  
 **Header:** „atldb.h“  
  
## Siehe auch  
 [Makros für OLE DB\-Anbietervorlagen](../../data/oledb/macros-for-ole-db-provider-templates.md)   
 [OLE DB\-Anbietervorlagen](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Architektur von OLE DB\-Anbietervorlagen](../../data/oledb/ole-db-provider-template-architecture.md)   
 [Erstellen eines OLE DB\-Anbieters](../../data/oledb/creating-an-ole-db-provider.md)
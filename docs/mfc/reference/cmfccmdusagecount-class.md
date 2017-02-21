---
title: "CMFCCmdUsageCount Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCCmdUsageCount"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCCmdUsageCount class"
ms.assetid: 9c33b783-37c0-43ea-9f31-3c75e246c841
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# CMFCCmdUsageCount Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Verfolgt die Verwendungsanzahl von Windows\-Meldungen, wie, wenn der Benutzer ein Element aus einem Menü auswählt.  
  
## Syntax  
  
```  
class CMFCCmdUsageCount : public CObject  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|||  
|-|-|  
|Name|Description|  
|`CMFCCmdUsageCount::CMFCCmdUsageCount`|Standardkonstruktor.|  
|`CMFCCmdUsageCount::~CMFCCmdUsageCount`|Destruktor.|  
  
### Öffentliche Methoden  
  
|||  
|-|-|  
|Name|Description|  
|[CMFCCmdUsageCount::AddCmd](../Topic/CMFCCmdUsageCount::AddCmd.md)|Inkremente durch eines der Indikator, der mit dem angegebenen Befehl zugeordnet ist.|  
|[CMFCCmdUsageCount::GetCount](../Topic/CMFCCmdUsageCount::GetCount.md)|Ruft die Verwendungsanzahl ab, die mit der angegebenen Befehl ID zugeordnet ist|  
|[CMFCCmdUsageCount::HasEnoughInformation](../Topic/CMFCCmdUsageCount::HasEnoughInformation.md)|Bestimmt, ob dieses Objekt die Mindestmenge von Nachverfolgungsdaten erfasst hat.|  
|[CMFCCmdUsageCount::IsFreqeuntlyUsedCmd](../Topic/CMFCCmdUsageCount::IsFreqeuntlyUsedCmd.md)|Bestimmt, ob der angegebene Befehl häufig verwendet wird.|  
|[CMFCCmdUsageCount::Reset](../Topic/CMFCCmdUsageCount::Reset.md)|Löscht die Verwendungsanzahl von allen Befehlen.|  
|[CMFCCmdUsageCount::Serialize](../Topic/CMFCCmdUsageCount::Serialize.md)|Liest dieses Objekt einem Archiv oder schreibt es einem Archiv.  \(Überschreibungen [CObject::Serialize](../Topic/CObject::Serialize.md).\)|  
|[CMFCCmdUsageCount::SetOptions](../Topic/CMFCCmdUsageCount::SetOptions.md)|Legt die Werte von freigegebenen `CMFCCmdUsageCount`\-Klassendatenmember fest.|  
  
### Datenmember  
  
|||  
|-|-|  
|Name|Description|  
|`m_CmdUsage`|Ein Objekt, das `CMap` Befehle zu ihrer Verwendung zuordnet, zählt.|  
|`m_nMinUsagePercentage`|Der minimale Verwendungsprozentsatz, damit ein Befehl häufig verwendet werden kann.|  
|`m_nStartCount`|Der Anfangsindikator, der verwendet wird, um zu bestimmen, ob dieses Objekt die Mindestmenge von Nachverfolgungsdaten erfasst hat.|  
|`m_nTotalUsage`|Die Anzahl aller verfolgten Befehle.|  
  
### Hinweise  
 Die `CMFCCmdUsageCount`\-Klasse ordnet jede numerische Windows\-Meldungs\-Nachrichtenkennung zu einem 32\-Bit\-Ganzzahl ohne Vorzeichen\-Indikator zu.  `CMFCToolBar` verwendet diese Klasse, um häufig verwendete Symbolleistenelemente anzuzeigen.  Weitere Informationen zur `CMFCToolBar`\-Komponente finden Sie unter [CMFCToolBar Class](../../mfc/reference/cmfctoolbar-class.md).  
  
 Sie können `CMFCCmdUsageCount`\-Klassendaten zwischen den einzelnen Ausführungen des Programms beibehalten.  Verwenden Sie die [CMFCCmdUsageCount::Serialize](../Topic/CMFCCmdUsageCount::Serialize.md)\-Methode, um Klassenmemberdaten und die [CMFCCmdUsageCount::SetOptions](../Topic/CMFCCmdUsageCount::SetOptions.md)\-Methode zu serialisieren, um freigegebene Memberdaten festzulegen.  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCCmdUsageCount](../../mfc/reference/cmfccmdusagecount-class.md)  
  
## Anforderungen  
 **Header:** afxcmdusagecount.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCToolBar Class](../../mfc/reference/cmfctoolbar-class.md)
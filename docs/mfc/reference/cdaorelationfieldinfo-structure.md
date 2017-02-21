---
title: "CDaoRelationFieldInfo-Struktur | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CDaoRelationFieldInfo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDaoRelationFieldInfo-Struktur"
  - "DAO (Datenzugriffsobjekte), Relations-Auflistung"
ms.assetid: 47cb89ca-dc80-47ce-96fd-cc4b88512558
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# CDaoRelationFieldInfo-Struktur
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die `CDaoRelationFieldInfo`\-Struktur enthält Informationen zu einem Feld in Beziehungen, die für Datenzugriffsobjekte \(DAO\) definiert ist.  
  
## Syntax  
  
```  
  
      struct CDaoRelationFieldInfo  
{  
   CString m_strName;           // Primary  
   CString m_strForeignName;    // Primary  
};  
```  
  
#### Parameter  
 `m_strName`  
 Der Name des Felds in der Beziehung.  
  
 `m_strForeignName`  
 Der Name des Felds in der fremden Tabelle der Beziehung.  
  
## Hinweise  
 Ein DAO\-Beziehungsobjekt sind die Felder in einer Tabelle und den Feldern in einer fremden Tabelle an, die die Beziehung definieren.  Die Verweise auf primärem in der obigen Strukturdefinition geben an, wie diese Informationen im `m_pFieldInfos`\-Member eines [CDaoRelationInfo](../../mfc/reference/cdaorelationinfo-structure.md)\-Objekts zurückgegeben werden, das mithilfe der Memberfunktion [GetRelationInfo](../Topic/CDaoDatabase::GetRelationInfo.md) der Klasse `CDaoDatabase` abgerufen wird, aufgerufen.  
  
 Beziehungsobjekte und Beziehungsfeldobjekte werden nicht durch eine MFC\-Klasse dargestellt.  Stattdessen enthält die DAO\-Objekte MFC\-Objekten, die der Klasse [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) zugrunde liegen, eine Auflistung Beziehungsobjekte, die aufgerufen Beziehungsauflistung.  Jedes Beziehungsobjekt enthält wiederum eine Auflistung Beziehungsfeldobjekte.  Jedes Beziehungsfeldobjekt besteht ein Feld in der Tabelle mit einem Feld in der fremden Tabelle aufeinander.  Zusammen entnommen, werden die Beziehungsfeldobjekte eine Gruppe Felder in jeder Tabelle, die zusammen die Beziehung definieren.  Mit `CDaoDatabase` können Sie auf Beziehungsobjekte mit `CDaoRelationInfo` zugreifen, Objekt, indem die `GetRelationInfo`\-Memberfunktion aufruft.  Das `CDaoRelationInfo`\-Objekt hat und dann ein Datenmember, `m_pFieldInfos`, der in einem Array `CDaoRelationFieldInfo`\-Objekten zeigt.  
  
 Rufen Sie die Memberfunktion [GetRelationInfo](../Topic/CDaoDatabase::GetRelationInfo.md) des enthaltenden `CDaoDatabase`\-Objekts auf, in dem Beziehungen Auflistung das Beziehungsobjekt gespeichert wird, das, Sie interessiert.  Informieren Sie dann das `m_pFieldInfos`[CDaoRelationInfo](../../mfc/reference/cdaorelationinfo-structure.md)\-Member des Objekts.  `CDaoRelationFieldInfo` definiert auch eine `Dump`\-Memberfunktion in Debugbuilds.  Sie können `Dump` verwenden, um den Inhalt eines `CDaoRelationFieldInfo`\-Objekts zu speichern.  
  
## Anforderungen  
 **Header:** afxdao.h  
  
## Siehe auch  
 [Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDaoRelationInfo\-Struktur](../../mfc/reference/cdaorelationinfo-structure.md)
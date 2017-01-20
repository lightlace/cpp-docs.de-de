---
title: "CDaoRelationInfo-Struktur"
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
  - "CDaoRelationInfo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDaoRelationInfo-Struktur"
  - "DAO (Datenzugriffsobjekte), Relations-Auflistung"
ms.assetid: 92dda090-fe72-4090-84ec-429498a48aad
caps.latest.revision: 13
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# CDaoRelationInfo-Struktur
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die `CDaoRelationInfo`\-Struktur enthält Informationen über eine Beziehung, der zwischen Feldern aus zwei Tabellen in einem [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md)\-Objekt definiert wird.  
  
## Syntax  
  
```  
  
      struct CDaoRelationInfo  
{  
   CDaoRelationInfo( );                    // Constructor  
   CString m_strName;                      // Primary  
   CString m_strTable;                     // Primary  
   CString m_strForeignTable;              // Primary  
   long m_lAttributes;                     // Secondary  
   CDaoRelationFieldInfo* m_pFieldInfos;   // Secondary  
   short m_nFields;                        // Secondary  
   // Below the // Implementation comment:  
   // Destructor, not otherwise documented  
};  
```  
  
#### Parameter  
 `m_strName`  
 Benennt eindeutig das Beziehungsobjekt.  Weitere Informationen finden Sie im Thema "Name\-Eigenschaft" in der DAO\-Hilfe.  
  
 *m\_strTable*  
 Benennt die Tabelle in der Beziehung.  
  
 *m\_strForeignTable*  
 Benennt die fremden Tabelle in der Beziehung.  Eine fremden Tabelle ist eine Tabelle, die verwendet wird, um Fremdschlüssel zu enthalten.  Im Allgemeinen verwenden Sie eine fremden Tabelle, um die referenzielle Integrität zu erstellen oder zu erzwingen.  Die fremden Tabelle ist normalerweise auf die n\-Seite einer 1: n\-Beziehung.  Beispiele für Fremdtabelleneinschließung Tabellen das Einbinden von Codes für die Zustände amerikanischen oder die kanadisches Provinzen oder die Kundenreihenfolgen.  
  
 `m_lAttributes`  
 Enthält Informationen zum Beziehungstyp.  Der Wert dieses Members kann eines der folgenden Elemente befinden:  
  
-   Beziehung ist **dbRelationUnique** erfolgt.  
  
-   Beziehung wird **dbRelationDontEnforce** nicht erzwungen keine \(referenzielle Integrität\).  
  
-   **dbRelationInherited** ist in einer Beziehung nicht aktuellen Datenbank, die die zwei umschlossenen Tabellen enthält.  
  
-   **dbRelationLeft** Die Beziehung ist ein linksjoin.  Ein linker äußerer Join enthält alle Datensätze vom ersten \(links\) aus zwei Tabellen, wenn es keine entsprechenden Werte nach Datensätzen in der zweiten Tabelle \(rechten\) gibt.  
  
-   **dbRelationRight** Die Beziehung ist ein Join rechts.  Ein rechten äußeren Join werden alle Datensätze des zweiten \(rechts\) aus zwei Tabellen, wenn es keine entsprechenden Werte nach Datensätzen in der ersten \(linken\) Tabelle gibt.  
  
-   **dbRelationUpdateCascade** Updates überlagern.  
  
-   **dbRelationDeleteCascade** Löschen kaskadiert.  
  
 `m_pFieldInfos`  
 Ein Zeiger auf ein Array [CDaoRelationFieldInfo](../../mfc/reference/cdaorelationfieldinfo-structure.md)\-Strukturen.  Das Array enthält ein Objekt für jedes Feld in der Beziehung.  Der `m_nFields` Datenmember gibt eine Anzahl der Arrayelemente.  
  
 `m_nFields`  
 Die Anzahl von `CDaoRelationFieldInfo` im `m_pFieldInfos` \- Datenmember ein.  
  
## Hinweise  
 Die Verweise auf primärem und einen sekundären oben genanntem geben an, wie die Informationen durch die [GetRelationInfo](../Topic/CDaoDatabase::GetRelationInfo.md)\-Memberfunktion in der `CDaoDatabase`\- Klasse zurückgegeben werden.  
  
 Beziehungsobjekte werden nicht durch eine MFC\-Klasse dargestellt.  Stattdessen wird das DAO\-Objekt, das ein MFC\-Objekt der `CDaoDatabase`\-Klasse liegt zugrunde, eine Auflistung Beziehungsobjekte bei: `CDaoDatabase` stellt Memberfunktionen, um auf mehrere einzelne Elemente aus Beziehungsinformationen zuzugreifen, oder Sie können mit einem `CDaoRelationInfo`\-Objekt in einem gemeinsam zugreifen, indem Sie die Memberfunktion `GetRelationInfo` des übergeordneten Datenbankobjekts aufrufen.  
  
 Die Informationen, die von der [CDaoDatabase::GetRelationInfo](../Topic/CDaoDatabase::GetRelationInfo.md)\-Memberfunktion aufgerufen werden, werden in einer `CDaoRelationInfo`\-Struktur gespeichert.  `CDaoRelationInfo` definiert auch eine `Dump`\-Memberfunktion in Debugbuilds.  Sie können `Dump` verwenden, um den Inhalt eines `CDaoRelationInfo`\-Objekts zu speichern.  
  
## Anforderungen  
 **Header:** afxdao.h  
  
## Siehe auch  
 [CDaoRelationFieldInfo\-Struktur](../../mfc/reference/cdaorelationfieldinfo-structure.md)
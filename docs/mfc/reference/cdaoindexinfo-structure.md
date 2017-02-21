---
title: "CDaoIndexInfo-Struktur | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CDaoIndexInfo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDaoIndexInfo-Struktur"
  - "DAO (Datenzugriffsobjekte), Auflistung von Indizes"
ms.assetid: 251d8285-78ce-4716-a0b3-ccc3395fc437
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# CDaoIndexInfo-Struktur
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die `CDaoIndexInfo`\-Struktur enthält Informationen dazu Indexobjekt, das für Datenzugriffsobjekte \(DAO\) definiert ist.  
  
## Syntax  
  
```  
  
      struct CDaoIndexInfo {  
   CDaoIndexInfo( );                   // Constructor  
   CString m_strName;                  // Primary  
   CDaoIndexFieldInfo* m_pFieldInfos;  // Primary  
   short m_nFields;                    // Primary  
   BOOL m_bPrimary;                    // Secondary  
   BOOL m_bUnique;                     // Secondary  
   BOOL m_bClustered;                  // Secondary  
   BOOL m_bIgnoreNulls;                // Secondary  
   BOOL m_bRequired;                   // Secondary  
   BOOL m_bForeign;                    // Secondary  
   long m_lDistinctCount;              // All  
  
   // Below the // Implementation comment:  
   // Destructor, not otherwise documented  
};   
```  
  
#### Parameter  
 `m_strName`  
 Benennt das eindeutig Feldobjekt.  Ausführliche Informationen finden Sie im Thema "Name\-Eigenschaft" in der DAO\-Hilfe.  
  
 `m_pFieldInfos`  
 Ein Zeiger auf ein Array von [CDaoIndexFieldInfo](../../mfc/reference/cdaoindexfieldinfo-structure.md)\-Objekte das Angeben ein, das Tabledef\- oder Recordsetfelder Schlüsselfelder in einem Index sind.  Jedes Objekt identifiziert ein Feld im Index.  Die Standardindexreihenfolge aufsteigend ist.  Ein Indexobjekt kann eine oder mehrere Felder verfügen, die Indexschlüssel für jeden Datensatz darstellen.  Diese können aufsteigend, weiter oder eine Kombination sein.  
  
 `m_nFields`  
 Die Anzahl von Feldern gespeichert in `m_pFieldInfos`.  
  
 *m\_bPrimary*  
 Wenn die primäre Eigenschaft **TRUE** ist, stellt das Primärindex Indexobjekt einen dar.  Ein Primärindex besteht aus einem oder mehreren Feldern eindeutig, die sämtliche Datensätze einer Tabelle in einer vordefinierten Reihenfolge identifizieren.  Da das Indexfeld eindeutig sein muss, wird die eindeutige Eigenschaft des Indexobjekts auch auf **TRUE** der DAO festgelegt.  Wenn der Primärindex aus mehr als einem Feld besteht, kann jedes Feld doppelte Werte enthalten, aber jede Kombination der Werte in allen indizierten Feldern muss eindeutig sein.  Ein Primärindex besteht aus einem Schlüssel für die Tabelle und enthält normalerweise die gleichen Felder wie der Primärschlüssel.  
  
 Wenn Sie einen Primärschlüssel für eine Tabelle, die Primärschlüssel automatisch wie der Primärindex für die Tabelle definiert werden.  Weitere Informationen finden Sie in den Themen "primäre Eigenschaft" und "Eigenschaft eindeutige" in der DAO\-Hilfe.  
  
> [!NOTE]
>  Es kann höchstens einen Primärindex auf einer Tabelle ein.  
  
 *m\_bUnique*  
 Gibt an, ob ein Indexobjekt einen eindeutigen Index für eine Tabelle darstellt.  Wenn diese Eigenschaft **TRUE** ist, stellt das Indexobjekt einen Index dar, der mehrdeutig ist.  Ein eindeutiger Index besteht aus einem oder mehreren Feldern, die logisch sämtliche Datensätze einer Tabelle einer eindeutigen, vordefinierten Reihenfolge anordnen.  Wenn der Index aus einem Feld besteht, müssen Werte in diesem Feld für die gesamte Tabelle eindeutig sein.  Wenn der Index aus mehr als einem Feld besteht, kann jedes Feld doppelte Werte enthalten, aber jede Kombination der Werte in allen indizierten Feldern muss eindeutig sein.  
  
 Wenn die eindeutige und primären Eigenschaften eines Indexobjekts auf **TRUE** festgelegt ist, ist der Index eindeutig und primär: Sie identifiziert eindeutig alle Datensätze in der Tabelle in einer vordefinierten, logischen Reihenfolge.  Wenn die primäre Eigenschaft auf **FALSE** festgelegt ist, ist der Index ein alternativer Schlüssel.  Alternative \(beide Schlüssel ver\- und Nicht\-Schlüssel\), ordnen logisch Datensätze in einer vordefinierten Reihenfolge, ohne als Bezeichner für Datensätze in der Tabelle verwenden.  
  
 Weitere Informationen finden Sie in den Themen "primäre Eigenschaft" und "Eigenschaft eindeutige" in der DAO\-Hilfe.  
  
 *m\_bClustered*  
 Gibt an, ob ein Indexobjekt einen gruppierten Index für eine Tabelle darstellt.  Wenn diese Eigenschaft **TRUE** ist, stellt das Indexobjekt einen gruppierten Index dar; Andernfalls führt es nicht.  Ein gruppierter Index besteht aus einem oder mehrere nicht um Schlüssel zu Feldern, mit denen zusammen entnommen, sämtliche Datensätze einer Tabelle in einer vordefinierten Reihenfolge anordnen.  Mit einem gruppierten Index werden die Daten in der Tabelle als solche in der Reihenfolge gespeichert, die von der gruppierten Index angegeben wird.  Ein gruppierter Index bietet effiziente Akteneinsicht in einer Tabelle.  Weitere Informationen finden Sie, dass das Thema "Eigenschaft" in der DAO\-Hilfe gruppierte.  
  
> [!NOTE]
>  Die gruppierten Eigenschaft wird ignoriert für Datenbanken, die das Microsoft Jet\-Datenbankmodul verwenden, da das Jet\-Datenbank\-Modul nicht gruppierter Indizes unterstützt.  
  
 *m\_bIgnoreNulls*  
 Gibt an, ob Indexeinträge für Datensätze gibt, die NULL\-Werte auf ihren Indexgebieten haben.  Wenn diese Eigenschaft **TRUE**, über Felder mit NULL\-Werten keinen Indexeintrag.  Um für Datensätze mithilfe eines Felds schneller finden zu machen, können Sie einen Index für das Feld definieren.  Wenn Sie ungültige Einträge auf einen indizierten Feld zulassen und zahlreiche Einträge erwarten, dass NULL zu sein, können Sie die IgnoreNulls\-Eigenschaft zum Indexobjekt zu **TRUE** festlegen, um den Speicherplatz reduzieren, den der Index verwendet.  Die IgnoreNulls\-Eigenschafteneinstellung und die erforderliche Einstellung bestimmt zusammen, ob ein Datensatz mit einem ungültigen Indexwert einen Indexeintrag verfügt, wie die folgende Tabelle zeigt.  
  
|IgnoreNulls|Erforderlich|NULL in dem Indexgebiet|  
|-----------------|------------------|-----------------------------|  
|True|False|NULL\-Wert zulässig; kein Indexeintrag hinzugefügt.|  
|False|False|NULL\-Wert zulässig; Indexeintrag hinzugefügt.|  
|True oder False|True|NULL\-Wert unzulässig; kein Indexeintrag hinzugefügt.|  
  
 Weitere Informationen finden Sie im Thema "IgnoreNulls\-Eigenschaft" in der DAO\-Hilfe.  
  
 `m_bRequired`  
 Gibt an, ob ein DAO\-Indexobjekt einen Wert ungleich null ist.  Wenn diese Eigenschaft **TRUE** ist, ermöglicht das Indexobjekt keinen NULL\-Wert.  Weitere Informationen finden Sie, dass das Thema "Eigenschaft" in der DAO\-Hilfe erforderlich.  
  
> [!TIP]
>  Wenn Sie diese Eigenschaft entweder für ein DAO\-Indexobjekt oder ein Feldobjekt festlegen können \(enthalten durch eine tabledef\-, ein Recordset oder ein Querydef\-Objekt\), legen Sie es für das Feldobjekt fest.  Die Gültigkeit der Eigenschafteneinstellung für ein Feldobjekt wird zuvor überprüft wird, die von einem Indexobjekt.  
  
 *m\_bForeign*  
 Gibt an, ob ein Indexobjekt einen Fremdschlüssel in einer Tabelle dar.  Wenn diese Eigenschaft **TRUE** ist, stellt der Index einen Fremdschlüssel in einer Tabelle dar.  Bei einem Fremdschlüssel besteht aus einem oder mehreren Feldern in einer eindeutig fremden Tabelle, die eine Zeile in einer Tabelle ermitteln.  Das Microsoft Jet\-Datenbankmodul erstellt ein Indexobjekt der fremden Tabelle und legt die fremde Eigenschaft fest, wenn Sie eine Beziehung erstellen, die referenzielle Integrität gewährleistet.  Weitere Informationen finden Sie im Thema "fremde Eigenschaft" in der DAO\-Hilfe.  
  
 *m\_lDistinctCount*  
 Gibt die Anzahl der eindeutigen Werte zum Indexobjekt angezeigt, die in der zugeordneten Tabelle enthalten sind.  Überprüfen Sie die DistinctCount\-Eigenschaft, um die eindeutigen Werte oder Schlüssel, in einem Index zu bestimmen.  Jede beliebige Taste wird nur einmal erfasst, obwohl sie mehrere Vorkommen dieses Werts gibt, wenn die Werte Indexerlaubnis dupliziert.  Diese Informationen sind nützlich in Anwendungen, die versuchen, den Datenzugriff zu optimieren, indem Indexinformationen auswerten.  Die Anzahl eindeutiger Werte ist auch als Kardinalität eines Indexobjekts.  Die DistinctCount\-Eigenschaft nicht immer wieder die tatsächliche Anzahl von Tasten zu einem bestimmten Zeitpunkt.  Beispielsweise wird eine Änderung, die durch ein Transaktionsrollback verursacht wird, nicht sofort in der DistinctCount\-Eigenschaft wiedergegeben.  Weitere Informationen finden Sie im Thema "DistinctCount\-Eigenschaft" in der DAO\-Hilfe.  
  
## Hinweise  
 Die Verweise auf primärem, und einen sekundären alle oben geben an, wie die Informationen durch die `GetIndexInfo`\-Memberfunktion in den Klassen [CDaoTableDef](../Topic/CDaoTableDef::GetIndexInfo.md) und [CDaoRecordset](../Topic/CDaoRecordset::GetIndexInfo.md) zurückgegeben werden.  
  
 Indexobjekte werden nicht durch eine MFC\-Klasse dargestellt.  Stattdessen DAO\-Objekte MFC\-Objekten enthalten, die der [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md) oder [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) zugrunde liegen, eine Auflistung Indexobjekte, die aufgerufen Indexauflistung.  Diese Klassen stellen Memberfunktionen, um auf einzelne Elemente aus Indexinformationen zuzugreifen, oder Sie können mit einem `CDaoIndexInfo`\-Objekt in einem gemeinsam zugreifen, indem Sie die Memberfunktion `GetIndexInfo` des enthaltenden Objekts aufrufen.  
  
 `CDaoIndexInfo` verfügt über einen Konstruktor und Destruktoren, um den Indexfeldinformationen in `m_pFieldInfos` korrekt zuzuordnen und freizugeben.  
  
 Die Informationen, die durch die `GetIndexInfo`\-Memberfunktion eines Tabledef\-Objekts abgerufen werden, werden in einer `CDaoIndexInfo`\-Struktur gespeichert.  Rufen Sie die Memberfunktion `GetIndexInfo` des enthaltenden Tabledef\-Objekts auf, in dessen Indexauflistung das Indexobjekt gespeichert wird.  `CDaoIndexInfo` definiert auch eine `Dump`\-Memberfunktion in Debugbuilds.  Sie können `Dump` verwenden, um den Inhalt eines `CDaoIndexInfo`\-Objekts zu speichern.  
  
## Anforderungen  
 **Header:** afxdao.h  
  
## Siehe auch  
 [Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDaoTableDef::GetIndexInfo](../Topic/CDaoTableDef::GetIndexInfo.md)
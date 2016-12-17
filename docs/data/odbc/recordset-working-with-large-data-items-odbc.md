---
title: "Recordset: Arbeiten mit gro&#223;en Datenelementen (ODBC)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Binary Large Objects (BLOBs)"
  - "BLOB (Binary Large Object), Recordsets"
  - "CLongBinary-Klasse, Verwenden in Recordsets"
  - "ODBC-Recordsets, Binary Large Objects (BLOBs)"
  - "Recordsets, Binary Large Objects (BLOBs)"
ms.assetid: 3e80b5a8-b6e7-43c6-a816-e54befc513a3
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Recordset: Arbeiten mit gro&#223;en Datenelementen (ODBC)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Dieses Thema bezieht sich auf die MFC\-ODBC\- und MFC\-DAO\-Klassen.  
  
> [!NOTE]
>  Wenn Sie die MFC\-DAO\-Klassen verwenden, sollten Sie große Datenelemente mit der Klasse [CByteArray](../../mfc/reference/cbytearray-class.md) verwalten statt mit der Klasse [CLongBinary](../../mfc/reference/clongbinary-class.md).  Falls Sie die MFC\-ODBC\-Klassen verwenden und das gesammelte Abrufen von Zeilen implementiert haben, verwenden Sie `CLongBinary` anstelle von `CByteArray`.  Weitere Informationen über das gesammelte Abrufen von Zeilen finden Sie unter [Recordset: Abrufen von Datensätzen in einer Sammeloperation \(ODBC\)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
 Nehmen wir an, die Datenbank kann große Datenelemente speichern, z. B. Bitmaps \(Photos der Mitarbeiter, Karten, Bilder der Produktpalette, OLE\-Objekte usw.\).  Diese Daten werden aus folgenden Gründen als große binäre Objekte bezeichnet \(Binary Large Objekt, BLOB\):  
  
-   Der Wert jedes Felds ist groß.  
  
-   Im Unterschied zu Zahlen und anderen einfachen Datenarten hat er keine feste Größe.  
  
-   Aus der Sicht des Programms besitzen die Daten keine Struktur.  
  
 In diesem Thema wird erläutert, welche Unterstützung die Datenbankklassen für die Verwendung solcher Objekte bieten.  
  
##  <a name="_core_managing_large_objects"></a> Verwalten großer Objekte  
 Recordsets können die speziellen Schwierigkeiten beim Umgang mit großen binären Objekten auf zwei Wegen lösen.  Sie können die [CByteArray](../../mfc/reference/cbytearray-class.md)\-Klasse oder die [CLongBinary](../../mfc/reference/clongbinary-class.md)\-Klasse verwenden.  Im Allgemeinen wird `CByteArray` für die Verwaltung großer binärer Daten verwendet.  
  
 `CByteArray` erfordert mehr Aufwand als `CLongBinary`, ist aber auch leistungsfähiger. Eine Beschreibung dieser Klasse finden Sie unter [CByteArray\-Klasse](#_core_the_cbytearray_class).  Eine kurze Beschreibung von `CLongBinary` finden Sie unter [CLongBinary\-Klasse](#_core_the_clongbinary_class).  
  
 Detaillierte Informationen über den Einsatz von `CByteArray` beim Umgang mit großen Datenelementen finden Sie in [Technischer Hinweis 45](../../mfc/tn045-mfc-database-support-for-long-varchar-varbinary.md).  
  
##  <a name="_core_the_cbytearray_class"></a> CByteArray\-Klasse  
 `CByteArray` ist eine der MFC\-Auflistungsklassen.  Ein `CByteArray`\-Objekt speichert ein dynamisches Bytearray, das also bei Bedarf größer werden kann.  Die Klasse bietet einen schnellen Zugriff über einen Index, genauso wie bei integrierten C\+\+\-Arrays.  `CByteArray`\-Objekte können serialisiert und zu Diagnosezwecken gesichert werden.  Die Klasse bietet Memberfunktionen zum Auslesen, Einstellen, Einfügen, Anhängen und Entfernen eines oder aller Bytes.  Diese Funktionen erleichtern das Durchsuchen der binären Daten.  Falls es sich bei dem binären Objekt z. B. um ein OLE\-Objekt handelt, finden Sie das eigentliche Objekt möglicherweise erst, nachdem Sie einige Headerbytes übersprungen haben.  
  
##  <a name="_core_using_cbytearray_in_recordsets"></a> CByteArray in Recordsets  
 Wenn Sie einem Felddatenmember des Recordsets den Typ `CByteArray` zuweisen, kann [RFX](../../data/odbc/record-field-exchange-rfx.md) die Übertragung eines Objekts zwischen dem Recordset und der Datenquelle durchführen. Außerdem ist es dann möglich, die Daten innerhalb des Objekts zu bearbeiten.  RFX benötigt einen bestimmten Speicherort für die abgerufenen Daten, und Sie benötigen eine Möglichkeit, auf die eigentlichen Daten zuzugreifen.  
  
 Detaillierte Informationen über den Einsatz von `CByteArray` beim Umgang mit großen Datenelementen finden Sie in [Technischer Hinweis 45](../../mfc/tn045-mfc-database-support-for-long-varchar-varbinary.md).  
  
##  <a name="_core_the_clongbinary_class"></a> CLongBinary\-Klasse  
 Ein [CLongBinary](../../mfc/reference/clongbinary-class.md)\-Objekt ist eine einfache Umgebung um ein `HGLOBAL`\-Handle, das auf einen Speicherblock auf dem Heap verweist.  Beim Binden einer Tabellenspalte, die ein großes binäres Objekt enthält, reserviert RFX das `HGLOBAL`\-Handle, wenn er Daten in das Recordset überträgt. Das Handle wird in dem `CLongBinary`\-Feld des Recordsets gespeichert.  
  
 Sie verwenden das **HGLOBAL\-**Handle `m_hData`, um auf die eigentlichen Daten zuzugreifen. Sie arbeiten damit wie mit jedem gewöhnlichen Handle.  Hierbei erweitert [CByteArray](../../mfc/reference/cbytearray-class.md) die Möglichkeiten.  
  
> [!CAUTION]
>  Sie können CLongBinary\-Objekte nicht als Parameter in Funktionsaufrufen verwenden.  Da in der Implementierung **::SQLGetData** aufgerufen wird, verlangsamt sich das Scrollen bei einer scrollbaren Momentaufnahme.  Dies kann auch dann gelten, wenn Sie selbst einen **::SQLGetData**\-Aufruf verwenden, um dynamische Schemaspalten abzufragen.  
  
## Siehe auch  
 [Recordset \(ODBC\)](../../data/odbc/recordset-odbc.md)   
 [Recordset: Abrufen von Summen und anderen Aggregatergebnissen \(ODBC\)](../../data/odbc/recordset-obtaining-sums-and-other-aggregate-results-odbc.md)   
 [Datensatzfeldaustausch \(RFX\)](../../data/odbc/record-field-exchange-rfx.md)
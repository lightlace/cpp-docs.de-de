---
title: "CLongBinary Class"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
f1_keywords: 
  - "BLOB"
  - "CLongBinary"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "BLOB (Binary Large Object)"
  - "BLOB (Binary Large Object), CLongBinary-Klasse"
  - "CLongBinary-Klasse"
ms.assetid: f4320059-aeb4-4ee5-bc2b-25f19d898ef5
caps.latest.revision: 21
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# CLongBinary Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Vereinfacht Funktion mit den sehr großen Binärdatenobjekten \(oft aufgerufen BLOB "oder" Binary Large Objects\) in einer Datenbank.  
  
## Syntax  
  
```  
class CLongBinary : public CObject  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CLongBinary::CLongBinary](../Topic/CLongBinary::CLongBinary.md)|Erstellt ein `CLongBinary`\-Objekt.|  
  
### Öffentliche Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[CLongBinary::m\_dwDataLength](../Topic/CLongBinary::m_dwDataLength.md)|Enthält das tatsächlichen Größe in Bytes des Datenobjekts, dessen Handle in `m_hData` gespeichert wird.|  
|[CLongBinary::m\_hData](../Topic/CLongBinary::m_hData.md)|Enthält ein Handle Windows `HGLOBAL` auf den tatsächlichen Bildobjekt.|  
  
## Hinweise  
 Zum Beispiel könnte ein Datensatzfeld in einer SQL\-Tabelle eine Bitmap, die ein Bild darstellt.  Ein Objekt speichert `CLongBinary` ein solches Objekt und behält seine Größe verfolgt.  
  
> [!NOTE]
>  Im Allgemeinen ist es bessere üblich, [CByteArray](../../mfc/reference/cbytearray-class.md) in Verbindung mit der [DFX\_Binary](../Topic/DFX_Binary.md)\-Funktion jetzt zu verwenden.  Sie können `CLongBinary` trotzdem verwenden, aber im Allgemeinen stellt `CByteArray` mehr Funktionen unter Win32 bereit, da es nicht mehr die Größeneinschränkung gibt, die mit 16\-Bit\-`CByteArray` erreicht wird.  Dieser Empfehlung gilt für die Programmierung mit Datenzugriffsobjekten \(DAO\) sowie zu Open Database Connectivity \(ODBC\).  
  
 Um ein `CLongBinary`\-Objekt zu verwenden, deklarieren Sie einen Felddatenmember des Typs `CLongBinary` in der Recordset\-Klasse.  Dieser Member ist ein eingebetteter Member der Recordset\-Klasse und wird erstellt, wenn das Recordset erstellt wird.  Nachdem das `CLongBinary`\-Objekt erstellt wurde, lädt der Mechanismus für den Datensatzfeldaustausch \(RFX\) das Datenobjekt aus einem Feld im aktuellen Datensatz der Datenquelle und speichert es an dem Datensatz, wenn der Datensatz aktualisiert wird.  RFX fragt die Datenquelle für die Größe des Binary Large Objects zuordnet, Speicher für sie \(über den `CLongBinary``m_hData` Datenmember des Objekts\) und speichert ein `HGLOBAL` Handle an Daten in `m_hData` ab.  RFX speichert auch die tatsächlichen Größe des Datenobjekts im `m_dwDataLength` Datenmember.  Arbeiten mit den Daten im Objekt durch `m_hData`, mit denselben Techniken, die normalerweise erledigen, um die Daten zu bearbeiten, die in einem Handle Windows `HGLOBAL` gespeichert wurden.  
  
 Wenn Sie das Recordset zerstören, ist das eingebettete `CLongBinary`\-Objekt auch zerstört, und der Destruktor gibt das `HGLOBAL` Datenhandle frei.  
  
 Weitere Informationen zu große Objekte und der Verwendung von `CLongBinary`, finden Sie in Artikel [Recordsets \(ODBC\)](../../data/odbc/recordset-odbc.md) und [Recordset: Arbeiten mit großen Datenelementen \(ODBC\)](../../data/odbc/recordset-working-with-large-data-items-odbc.md).  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CLongBinary`  
  
## Anforderungen  
 **Header:**  afxdb\_.h  
  
## Siehe auch  
 [CObject Class](../../mfc/reference/cobject-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CRecordset Class](../../mfc/reference/crecordset-class.md)
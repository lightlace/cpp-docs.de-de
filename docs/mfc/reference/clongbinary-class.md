---
title: CLongBinary-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CLongBinary
- AFXDB_/CLongBinary
- AFXDB_/CLongBinary::CLongBinary
- AFXDB_/CLongBinary::m_dwDataLength
- AFXDB_/CLongBinary::m_hData
dev_langs:
- C++
helpviewer_keywords:
- BLOB (binary large object)
- CLongBinary class
- BLOB (binary large object), CLongBinary class
ms.assetid: f4320059-aeb4-4ee5-bc2b-25f19d898ef5
caps.latest.revision: 21
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: bb73604ee4d15f3a71be8514f348ad265064928a
ms.lasthandoff: 02/24/2017

---
# <a name="clongbinary-class"></a>CLongBinary-Klasse
Vereinfacht die Verwendung sehr großen Binärdatenobjekte (oft "BLOBs" oder "Binary Large Objects" genannt) in einer Datenbank.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CLongBinary : public CObject  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CLongBinary::CLongBinary](#clongbinary)|Erstellt ein `CLongBinary`-Objekt.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CLongBinary::m_dwDataLength](#m_dwdatalength)|Enthält die tatsächliche Größe in Bytes des Objekts, dessen Handle sich in befindet `m_hData`.|  
|[CLongBinary::m_hData](#m_hdata)|Enthält eine Windows `HGLOBAL` handle für das eigentliche Bild-Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 Beispielsweise enthalten ein Datensatzfeld in einer SQL-Tabelle eine Bitmap, ein Bild darstellt. Ein `CLongBinary` Objekt speichert ein solches Objekt und verfolgt seine Größe.  
  
> [!NOTE]
>  Im Allgemeinen ist es jetzt empfehlenswert, verwenden Sie [CByteArray](../../mfc/reference/cbytearray-class.md) in Verbindung mit der [DFX_Binary](http://msdn.microsoft.com/library/678021a3-2e46-44d7-8528-71bb692dcc07) Funktion. Sie können weiterhin verwenden `CLongBinary`, aber im allgemeinen `CByteArray` bietet mehr Funktionen unter Win32, da es nicht mehr ist das Größenlimit mit dem 16-Bit- `CByteArray`. Diese Empfehlung gilt für die Programmierung mit Datenzugriffsobjekte (DAO) als auch für Open Database Connectivity (ODBC).  
  
 Verwenden einer `CLongBinary` -Objekt, deklarieren einen Felddatenmember vom Typ `CLongBinary` in die Recordset-Klasse. Dieser Member ist ein eingebettetes Element der Recordset-Klasse und wird erstellt, wenn das Recordset erstellt wird. Nach der `CLongBinary` Objekt erstellt wird, den Datensatzfeldaustausch (RFX)-Mechanismus lädt das Objekt aus einem Feld im aktuellen Datensatz in der Datenquelle und zurück auf den Datensatz gespeichert, wenn der Datensatz aktualisiert wird. RFX Abfragen die Datenquelle, für die Größe der binary large Object, weist Speicher für sie (über die `CLongBinary` des Objekts `m_hData` -Datenmember), und speichert eine `HGLOBAL` handle für die Daten in `m_hData`. RFX speichert auch die tatsächliche Größe des Objekts in der `m_dwDataLength` -Datenmember. Arbeiten mit den Daten in das Objekt über `m_hData`, mit den gleichen Verfahren normalerweise würden Sie verwenden zum Bearbeiten von Daten in einer Windows `HGLOBAL` behandeln.  
  
 Beim Zerstören Sie des Recordsets, das eingebettete `CLongBinary` auch-Objekt zerstört wird, und hebt die Zuordnung der Destruktor der `HGLOBAL` Daten Handle.  
  
 Weitere Informationen zu großen Objekten und die Verwendung von `CLongBinary`, finden Sie in den Artikeln [Recordset (ODBC)](../../data/odbc/recordset-odbc.md) und [Recordset: Arbeiten mit großen von Elementen (ODBC)](../../data/odbc/recordset-working-with-large-data-items-odbc.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 `CLongBinary`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxdb_.h  
  
##  <a name="clongbinary"></a>CLongBinary::CLongBinary  
 Erstellt ein `CLongBinary`-Objekt.  
  
```  
CLongBinary();
```  
  
##  <a name="m_dwdatalength"></a>CLongBinary::m_dwDataLength  
 Speichert die tatsächliche Größe in Bytes der Daten in der `HGLOBAL` in behandelt `m_hData`.  
  
```  
SQLULEN m_dwDataLength;  
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Größe möglicherweise kleiner als die Größe des Speicherblocks, für die Daten zugeordnet. Rufen Sie die Win32 [GlobalSize ist](http://msdn.microsoft.com/library/windows/desktop/aa366593) Funktion, um die zugeordnete Größe abzurufen.  
  
##  <a name="m_hdata"></a>CLongBinary::m_hData  
 Speichert eine Windows `HGLOBAL` an den tatsächlichen BLOB-Daten behandelt.  
  
```  
HGLOBAL m_hData;  
```  
  
## <a name="see-also"></a>Siehe auch  
 [CObject-Klasse](../../mfc/reference/cobject-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CRecordset-Klasse](../../mfc/reference/crecordset-class.md)


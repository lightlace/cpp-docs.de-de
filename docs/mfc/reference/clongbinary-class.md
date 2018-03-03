---
title: CLongBinary-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
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
- CLongBinary class [MFC]
ms.assetid: f4320059-aeb4-4ee5-bc2b-25f19d898ef5
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 49661932192a32550d50edfbbc52d7967cb78dcd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="clongbinary-class"></a>CLongBinary-Klasse
Vereinfacht die Verwendung sehr großen Binärdatenobjekte (oft "BLOBs" oder "Binary Large Objects" genannt) in einer Datenbank.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CLongBinary : public CObject  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CLongBinary::CLongBinary](#clongbinary)|Erstellt ein `CLongBinary`-Objekt.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CLongBinary::m_dwDataLength](#m_dwdatalength)|Enthält die tatsächliche Größe in Bytes des Datenobjekts, dessen Handle sich in befindet `m_hData`.|  
|[CLongBinary::m_hData](#m_hdata)|Enthält einen Windows `HGLOBAL` handle für das aktuelle Image-Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 Beispielsweise enthalten ein Datensatzfeld in einer SQL-Tabelle eine Bitmap, ein Bild darstellt. Ein `CLongBinary` Objekt speichert ein solches Objekt und verfolgt seine Größe.  
  
> [!NOTE]
>  Im Allgemeinen ist es besser empfohlen, jetzt auf [CByteArray](../../mfc/reference/cbytearray-class.md) in Verbindung mit der [DFX_Binary](record-field-exchange-functions.md#dfx_binary) Funktion. Sie können weiterhin `CLongBinary`, aber im allgemeinen `CByteArray` bietet mehr Funktionen unter Win32, da es nicht mehr ist die maximale Datenbankgröße bei Verwendung von 16-Bit- `CByteArray`. Diese Empfehlung gilt, mit dem Programmieren mit Datenzugriffsobjekte (DAO) als auch Open Database Connectivity (ODBC).  
  
 Verwenden einer `CLongBinary` -Objekt, einen Felddatenmember des Typs deklarieren `CLongBinary` im Recordset-Klasse. Dieser Member ein eingebettetes Element der Recordset-Klasse werden und wird erstellt, wenn das Recordset erstellt wird. Nach der `CLongBinary` Objekt erstellt wurde, die Datensatzfeldaustausch (RFX)-Mechanismus lädt das Datenobjekt von einem Feld im aktuellen Datensatz in der Datenquelle und zurück auf den Datensatz gespeichert, wenn der Datensatz aktualisiert wurde. RFX fragt die Datenquelle aus, für die Größe der binary large Object, weist Speicher für er (über die `CLongBinary` des Objekts `m_hData` -Datenmember), und speichert eine `HGLOBAL` handle für die Daten in `m_hData`. RFX speichert auch die tatsächliche Größe des Datenobjekts in der `m_dwDataLength` -Datenmember. Arbeiten mit den Daten in diesem Objekt über `m_hData`, dabei werden dieselben Methoden normalerweise würden Sie verwenden zum Bearbeiten der Daten in einer Windows gespeichert `HGLOBAL` behandeln.  
  
 Beim Zerstören Sie des Recordsets, das eingebettete `CLongBinary` auch-Objekt zerstört wird und der Destruktor hebt die Zuordnung der `HGLOBAL` Daten Handle.  
  
 Weitere Informationen zu großen Objekten und die Verwendung von `CLongBinary`, finden Sie in den Artikeln [Recordset (ODBC)](../../data/odbc/recordset-odbc.md) und [Recordset: Arbeiten mit großen von Elementen (ODBC)](../../data/odbc/recordset-working-with-large-data-items-odbc.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CLongBinary`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxdb_.h  
  
##  <a name="clongbinary"></a>CLongBinary::CLongBinary  
 Erstellt ein `CLongBinary`-Objekt.  
  
```  
CLongBinary();
```  
  
##  <a name="m_dwdatalength"></a>CLongBinary::m_dwDataLength  
 Die tatsächliche Größe in Bytes, der gespeicherten Daten speichert die `HGLOBAL` in behandelt `m_hData`.  
  
```  
SQLULEN m_dwDataLength;  
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Größe kann kleiner als die Größe des Speicherblocks, der für die Daten zugeordnet werden. Rufen Sie die Win32 [GlobalSize ist](http://msdn.microsoft.com/library/windows/desktop/aa366593) Funktion zum Abrufen der zugeordneten Größe.  
  
##  <a name="m_hdata"></a>CLongBinary::m_hData  
 Speichert eine Windows `HGLOBAL` handle für die tatsächliche binary large Object-Daten.  
  
```  
HGLOBAL m_hData;  
```  
  
## <a name="see-also"></a>Siehe auch  
 [CObject-Klasse](../../mfc/reference/cobject-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CRecordset-Klasse](../../mfc/reference/crecordset-class.md)

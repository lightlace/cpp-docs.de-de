---
title: CRestrictions-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL::CRestrictions
- CRestrictions
- ATL.CRestrictions
- CRestrictions.Open
- ATL::CRestrictions::Open
- ATL.CRestrictions.Open
- CRestrictions::Open
dev_langs:
- C++
helpviewer_keywords:
- CRestrictions class
- Open method
ms.assetid: 0aaa2364-641c-4318-b110-7446aada4b4f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: a4ea0536a8af87927521f88d888e19aa145f2c04
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50072069"
---
# <a name="crestrictions-class"></a>CRestrictions-Klasse

Eine generische Klasse, die Sie Einschränkungen für Schemarowsets angeben kann.

## <a name="syntax"></a>Syntax

```cpp
template <class T, short nRestrictions, const GUID* pguid>
class CRestrictions :
   public CSchemaRowset <T, nRestrictions>
```

### <a name="parameters"></a>Parameter

*T*<br/>
Die Klasse, die für den Accessor verwendet wird.

*nRestrictions*<br/>
Die Anzahl der Einschränkungsspalten für das Schemarowset.

*pguid*<br/>
Ein Zeiger auf die GUID für das Schema.

## <a name="requirements"></a>Anforderungen

**Header:** atldbsch.h

## <a name="members"></a>Member

### <a name="methods"></a>Methoden

|||
|-|-|
|[Öffnen](#open)|Gibt ein Resultset, die gemäß den vom Benutzer anzugebende Einschränkungen zurück.|

## <a name="open"></a> CRestrictions:: Open

Gibt ein Resultset, die gemäß den vom Benutzer anzugebende Einschränkungen zurück.

### <a name="syntax"></a>Syntax

```cpp
HRESULT Open(const CSession& session,
   LPCTSTR lpszParam 1 = NULL,
   LPCTSTR lpszParam 2 = NULL,
   LPCTSTR lpszParam 3 = NULL,
   LPCTSTR lpszParam 4 = NULL,
   LPCTSTR lpszParam 5 = NULL,
   LPCTSTR lpszParam 6 = NULL,
   LPCTSTR lpszParam 7 = NULL,
   bool bBind = true);
```

#### <a name="parameters"></a>Parameter

*Sitzung*<br/>
[in] Gibt ein vorhandenes Session-Objekt, das für die Verbindung mit der Datenquelle verwendet.

*lpszParam*<br/>
[in] Gibt die Einschränkungen für das Schemarowset.

*bBind*<br/>
[in] Gibt an, ob die spaltenzuordnung automatisch zu binden. Der Standardwert ist **"true"**, der bewirkt, dass der spaltenzuordnung automatisch gebunden werden soll. Festlegen von *bBind* zu **"false"** wird verhindert, dass die automatische Bindung der Spalte-Zuordnung aus, damit Sie manuell binden können. (Manuelle Bindung ist von besonderem Interesse für OLAP-Benutzer.)

### <a name="return-value"></a>Rückgabewert

Einer der standardmäßigen HRESULT-Werte.

### <a name="remarks"></a>Hinweise

Sie können maximal sieben Einschränkungen für ein Schemarowset angeben.

Finden Sie unter [IDBSchemaRowset](/previous-versions/windows/desktop/ms713686) für Informationen zu den definierten Einschränkungen für jedes Schemarowset.

## <a name="see-also"></a>Siehe auch

[OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[Referenz der OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-reference.md)<br/>
[Schemarowset-Klassen und Typedef-Klassen](../../data/oledb/schema-rowset-classes-and-typedef-classes.md)
---
title: CDaoRelationInfo-Struktur
ms.date: 06/25/2018
f1_keywords:
- CDaoRelationInfo
helpviewer_keywords:
- DAO (Data Access Objects), Relations collection
- CDaoRelationInfo structure [MFC]
ms.assetid: 92dda090-fe72-4090-84ec-429498a48aad
ms.openlocfilehash: 7d1c86732966d8222582dc6d4527af89963a5cdc
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57274972"
---
# <a name="cdaorelationinfo-structure"></a>CDaoRelationInfo-Struktur

Die `CDaoRelationInfo` Struktur enthält Informationen über eine Beziehung zwischen den Feldern von zwei Tabellen in definiert eine [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) Objekt.

## <a name="syntax"></a>Syntax

```cpp
struct CDaoRelationInfo
{
    CDaoRelationInfo();                     // Constructor
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

#### <a name="parameters"></a>Parameter

*m_strName*<br/>
Eindeutig bezeichnet die Relation-Objekt. Weitere Informationen finden Sie im Thema "Name-Eigenschaft" in-DAO-Hilfe.

*m_strTable*<br/>
Gibt den Namen der primären Tabelle in der Beziehung.

*m_strForeignTable*<br/>
Gibt den Namen der fremden Tabelle in der Beziehung. Fremdtabelle ist eine Tabelle verwendet, um die Fremdschlüssel enthalten. Im Allgemeinen verwenden Sie Fremdtabelle hergestellt oder die referenzielle Integrität erzwingen. Die fremde Tabelle ist in der Regel auf der n-Seite einer 1: n Beziehung. Beispiele für fremden Tabellen sind Tabellen, die Codes für das American Zustände oder kanadischen Provinzen oder kundenbestellungen enthalten.

*m_lAttributes*<br/>
Enthält Informationen zu den Beziehungstyp. Der Wert dieses Members kann es sich um eine der folgenden sein:

- `dbRelationUnique` Besteht eine 1: 1-Beziehung.

- `dbRelationDontEnforce` Beziehung wird nicht erzwungen (keine referenzielle Integrität).

- `dbRelationInherited` Beziehung in einer nicht aktuellen Datenbank mit den beiden angefügten Tabellen vorhanden ist.

- `dbRelationLeft` Die Beziehung ist ein Linker Join. Eine linke äußere Verknüpfung enthält alle Datensätze aus der ersten (linken) der beiden Tabellen, auch wenn keine übereinstimmenden Werte für Datensätze in der zweiten (rechten) Tabelle vorhanden sind.

- `dbRelationRight` Die Beziehung ist eine richtige Join. Ein rechter äußerer Join schließt alle Datensätze aus der zweiten (rechten) der beiden Tabellen, auch wenn keine übereinstimmenden Werte für Datensätze in der ersten (linken) Tabelle vorhanden sind.

- `dbRelationUpdateCascade` Updates kaskadieren.

- `dbRelationDeleteCascade` Löschvorgänge werden weitergegeben.

*m_pFieldInfos*<br/>
Ein Zeiger auf ein Array von [CDaoRelationFieldInfo](../../mfc/reference/cdaorelationfieldinfo-structure.md) Strukturen. Das Array enthält ein Objekt für jedes Feld in der Beziehung. Die `m_nFields` Datenmember gibt die Anzahl der Elemente des Arrays.

*m_nFields*<br/>
Die Anzahl der `CDaoRelationFieldInfo` Objekte in der `m_pFieldInfos` -Datenmember.

## <a name="remarks"></a>Hinweise

Die Verweise auf primären und sekundären Datenbank, die oben genannten anzugeben, wie die Informationen zurückgegeben werden, indem die [GetRelationInfo](../../mfc/reference/cdaodatabase-class.md#getrelationinfo) Memberfunktion in Klasse `CDaoDatabase`.

Relation-Objekte werden nicht von einer MFC-Klasse dargestellt. Stattdessen, die DAO-Objekt, das zugrunde liegende ein MFC-Objekt, der die `CDaoDatabase` -Klasse verwaltet eine Auflistung von Objekten der Beziehung: `CDaoDatabase` stellt Memberfunktionen den Zugriff auf einige einzelne Elemente Beziehung Informationen, oder wenn Sie darauf zugreifen können gleichzeitig mit einer `CDaoRelationInfo` -Objekt durch Aufrufen der `GetRelationInfo` Memberfunktion Rand des enthaltenden Objekts für die Datenbank.

Informationen, die abgerufen, indem die [CDaoDatabase::GetRelationInfo](../../mfc/reference/cdaodatabase-class.md#getrelationinfo) Member-Funktion befindet sich in einem `CDaoRelationInfo` Struktur. `CDaoRelationInfo` definiert auch eine `Dump` -Memberfunktion im Debug-builds. Können Sie `Dump` zum Sichern den Inhalt einer `CDaoRelationInfo` Objekt.

## <a name="requirements"></a>Anforderungen

**Header:** afxdao.h

## <a name="see-also"></a>Siehe auch

[CDaoRelationFieldInfo-Struktur](../../mfc/reference/cdaorelationfieldinfo-structure.md)

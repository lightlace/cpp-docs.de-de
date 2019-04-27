---
title: CDaoRelationFieldInfo-Struktur
ms.date: 11/04/2016
f1_keywords:
- CDaoRelationFieldInfo
helpviewer_keywords:
- DAO (Data Access Objects), Relations collection
- CDaoRelationFieldInfo structure [MFC]
ms.assetid: 47cb89ca-dc80-47ce-96fd-cc4b88512558
ms.openlocfilehash: 85dd853a9aae41a87bbe7ef5c69e22846678cf8a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62206107"
---
# <a name="cdaorelationfieldinfo-structure"></a>CDaoRelationFieldInfo-Struktur

Die `CDaoRelationFieldInfo` Struktur enthält Informationen über ein Feld in einer Beziehung für Datenzugriffsobjekte (DAO) definiert.

## <a name="syntax"></a>Syntax

```
struct CDaoRelationFieldInfo
{
    CString m_strName;           // Primary
    CString m_strForeignName;    // Primary
};
```

#### <a name="parameters"></a>Parameter

*m_strName*<br/>
Der Name des Felds in der primären Tabelle der Beziehung.

*m_strForeignName*<br/>
Der Name des Felds in der fremden Tabelle der Beziehung.

## <a name="remarks"></a>Hinweise

Ein DAO-Relation-Objekt gibt die Felder in einer primären Tabelle und die Felder in einer Fremdschlüsseltabelle, die die Beziehung zu definieren. Die Verweise auf primären in die obige Strukturdefinition anzugeben, wie die Informationen zurückgegeben werden, in der `m_pFieldInfos` Mitglied einer [CDaoRelationInfo](../../mfc/reference/cdaorelationinfo-structure.md) Objekt durch den Aufruf der [GetRelationInfo](../../mfc/reference/cdaodatabase-class.md#getrelationinfo)Memberfunktion der Klasse `CDaoDatabase`.

Beziehung und Beziehung Feldobjekte werden nicht von einer MFC-Klasse dargestellt. Stattdessen Objekte zum DAO zugrunde liegenden MFC-Objekte der Klasse [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) enthalten eine Auflistung von Objekten von Beziehung, die Relations-Auflistung aufgerufen. Jedes Beziehungsobjekt enthält wiederum eine Auflistung von Objekten der Beziehung-Feld. Jedes Feld Beziehungsobjekt korreliert ein Feld in der primären Tabelle mit einem Feld in der Fremdschlüsseltabelle. Zusammen genommen definieren Objekte die Beziehung Feld eine Gruppe von Feldern in jeder Tabelle, die zusammen die Beziehung zu definieren. `CDaoDatabase` ermöglicht den Zugriff auf Beziehungsobjekte mit einer `CDaoRelationInfo` -Objekt durch Aufrufen der `GetRelationInfo` Member-Funktion. Die `CDaoRelationInfo` Objekt hat dann einen Datenmember `m_pFieldInfos`, verweist auf ein Array von `CDaoRelationFieldInfo` Objekte.

Rufen Sie die [GetRelationInfo](../../mfc/reference/cdaodatabase-class.md#getrelationinfo) -Memberfunktion des enthaltenden `CDaoDatabase` Objekt, in deren Beziehungen, die Auflistung ist die Relation-Objekt gespeichert Sie interessiert sind. Öffnen Sie dann die `m_pFieldInfos` Mitglied der [CDaoRelationInfo](../../mfc/reference/cdaorelationinfo-structure.md) Objekt. `CDaoRelationFieldInfo` definiert auch eine `Dump` -Memberfunktion im Debug-builds. Können Sie `Dump` zum Sichern den Inhalt einer `CDaoRelationFieldInfo` Objekt.

## <a name="requirements"></a>Anforderungen

**Header:** afxdao.h

## <a name="see-also"></a>Siehe auch

[Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CDaoRelationInfo-Struktur](../../mfc/reference/cdaorelationinfo-structure.md)

---
title: CDaoIndexInfo-Struktur
ms.date: 06/25/2018
f1_keywords:
- CDaoIndexInfo
helpviewer_keywords:
- DAO (Data Access Objects), Indexes collection
- CDaoIndexInfo structure [MFC]
ms.assetid: 251d8285-78ce-4716-a0b3-ccc3395fc437
ms.openlocfilehash: 55f64fcebc308bd0e63643cfb5447608c4e2e37c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62399771"
---
# <a name="cdaoindexinfo-structure"></a>CDaoIndexInfo-Struktur

Die `CDaoIndexInfo` Struktur enthält Informationen zu einem Indexobjekt, das für Datenzugriffsobjekte (DAO) definiert.

## <a name="syntax"></a>Syntax

```cpp
struct CDaoIndexInfo {
    CDaoIndexInfo();                    // Constructor
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

### <a name="parameters"></a>Parameter

*m_strName*<br/>
Eindeutig bezeichnet das Field-Objekt. Informationen finden Sie im Thema "Name-Eigenschaft" in-DAO-Hilfe.

*m_pFieldInfos*<br/>
Ein Zeiger auf ein Array von [CDaoIndexFieldInfo](../../mfc/reference/cdaoindexfieldinfo-structure.md) Objekte, der angibt, welche Felder Tabledef oder ein Recordset Schlüsselfelder in einem Index sind. Jedes Objekt gibt ein Feld im Index. Der Index Standardreihenfolge ist Aufsteigend. Ein Indexobjekt kann es sich um ein oder mehrere Felder, die Index-Schlüssel für jeden Datensatz darstellt aufweisen. Diese können, absteigend, oder eine Kombination aufsteigend sortiert sein.

*m_nFields*<br/>
Die Anzahl der Felder, die in gespeicherten `m_pFieldInfos`.

*m_bPrimary*<br/>
Wenn die Primärschlüssel-Eigenschaft TRUE ist, stellt das Indexobjekt einen primären Index dar. Ein primärer Index besteht aus einem oder mehreren Feldern, die alle Datensätze in einer Tabelle in einer vordefinierten Reihenfolge eindeutig zu identifizieren. Da der Index-Feld eindeutig sein muss, wird die Unique-Eigenschaft des Indexobjekts ebenfalls auf "true" in-DAO-festgelegt. Wenn der primäre Index von mehr als ein Feld besteht, jedes Feld kann doppelte Werte enthalten, aber jede Kombination von Werten alle indizierten Felder muss eindeutig sein. Ein primärer Index besteht aus einem Schlüssel für die Tabelle und in der Regel die gleichen Felder wie den primären Schlüssel enthält.

Wenn Sie einen Primärschlüssel für eine Tabelle festlegen, wird der primäre Schlüssel automatisch als primärer Index für die Tabelle definiert. Weitere Informationen finden Sie unter den Themen "Primäre Property" und "Eindeutige Eigenschaft" in-DAO-Hilfe.

> [!NOTE]
> Es kann sein, höchstens ein primärer Index für eine Tabelle.

*m_bUnique*<br/>
Gibt an, ob ein Indexobjekt einen eindeutigen Index für eine Tabelle darstellt. Ist diese Eigenschaft auf "true", stellt das Indexobjekt einen Index, der eindeutig ist. Ein eindeutiger Index besteht aus einem oder mehreren Feldern, die logisch alle Datensätze in einer Tabelle in einen eindeutigen, vordefinierten Reihenfolge anordnen. Wenn der Index eines Felds besteht, müssen Werte im Feld für die gesamte Tabelle eindeutig sein. Wenn der Index von mehr als ein Feld besteht, jedes Feld kann doppelte Werte enthalten, aber jede Kombination von Werten alle indizierten Felder muss eindeutig sein.

Wenn die Unique- und die primären Eigenschaften eines Indexobjekts auf "true" festgelegt werden, ist der Index Unique- und primary: Alle Datensätze in der Tabelle in einer vordefinierten, logischen Reihenfolge identifiziert eindeutig. Wenn die Primärschlüssel-Eigenschaft auf "false" festgelegt ist, ist der Index ein sekundärer Index. Sekundäre Indizes (Schlüssel oder nichtschlüssel) ordnen logisch Datensätze in einer vordefinierten Reihenfolge ohne als Bezeichner für die Datensätze in der Tabelle zu dienen.

Weitere Informationen finden Sie unter den Themen "Primäre Property" und "Eindeutige Eigenschaft" in-DAO-Hilfe.

*m_bClustered*<br/>
Gibt an, ob ein Indexobjekt über einen gruppierten Index für eine Tabelle darstellt. Wenn diese Eigenschaft auf "true" ist, stellt das Indexobjekt einen gruppierten Index; Andernfalls ist es nicht. Ein gruppierter Index besteht aus einem oder mehreren Nichtschlüsselfeldern, ordnen Sie alle Datensätze in einer Tabelle in einer vordefinierten Reihenfolge zusammen. Mit einem gruppierten Index ist die Daten in der Tabelle wörtlich in der Reihenfolge angegeben, die vom gruppierten Index gespeichert. Ein gruppierter Index, bietet effizienten Zugriff auf Datensätze in einer Tabelle. Weitere Informationen finden Sie im Thema "Clustered-Eigenschaft" in-DAO-Hilfe.

> [!NOTE]
> Für Datenbanken, die die Microsoft Jet-Datenbank-Engine zu verwenden, da die Jet-Datenbank-Engine nicht gruppierte Indizes unterstützt wird, wird die Clustered-Eigenschaft ignoriert.

*m_bIgnoreNulls*<br/>
Gibt an, ob es Indexeinträge für Datensätze, die Null-Werte in ihren Indexfeldern zu haben. Wenn diese Eigenschaft auf "true" ist, müssen Felder mit Null-Werten einen Indexeintrag keine. Zum Suchen nach Datensätzen, die mithilfe eines Felds schneller zu machen, können Sie einen Index für das Feld definieren. Wenn Sie Einträge in einem indizierten Feld Null zulassen und erwarten, dass viele Einträge Null sein kann, können Sie die IgnoreNulls-Eigenschaft für das Indexobjekt festlegen, auf "true", um die Menge an Speicherplatz zu reduzieren, die den Index verwendet. Die Einstellung der Eigenschaft IgnoreNulls und die Einstellung der erforderlichen Eigenschaft bestimmen zusammen, ob ein Datensatz mit einem Indexwert von Null Indexeintrag, wie der folgenden Tabelle gezeigt hat.

|IgnoreNulls|Erforderlich|NULL, im Feld "Index"|
|-----------------|--------------|-------------------------|
|True|False|NULL-Wert zulässig Es wurden keine Indexeintrag hinzugefügt.|
|False|False|NULL-Wert zulässig Indexeintrag hinzugefügt.|
|True oder False|True|NULL-Wert nicht zulässig Es wurden keine Indexeintrag hinzugefügt.|

Weitere Informationen finden Sie im Thema "IgnoreNulls-Eigenschaft" in-DAO-Hilfe.

*m_bRequired*<br/>
Gibt an, ob ein DAO-Index-Objekt einen Wert ungleich Null erfordert. Wenn diese Eigenschaft auf "true" ist, lässt das Indexobjekt keinen Null-Wert. Weitere Informationen finden Sie im Thema "Erforderliche Eigenschaft" in-DAO-Hilfe.

> [!TIP]
> Wenn Sie diese Eigenschaft für ein DAO-Index-Objekt oder ein Field-Objekt (eine Tabledef, Querydef-Objekt oder ein Recordset enthalten) festlegen können, legen Sie sie für das Field-Objekt. Die Gültigkeit der eigenschafteneinstellung für ein Objekt des Felds wird vor einer Index-Objekt überprüft.

*m_bForeign*<br/>
Gibt an, ob ein Indexobjekt einen Fremdschlüssel in einer Tabelle darstellt. Wenn diese Eigenschaft auf "true" ist, stellt der Index einen Fremdschlüssel in einer Tabelle dar. Ein Fremdschlüssel besteht aus einem oder mehreren Feldern in einer Fremdschlüsseltabelle, die eine Zeile in einer primären Tabelle eindeutig identifizieren. Die Microsoft Jet-Datenbank-Engine erstellt ein Indexobjekt für die Fremdtabelle und legt die Fremdschlüssel-Eigenschaft fest, wenn Sie eine Beziehung erstellen, die referenzielle Integrität gewährleistet. Weitere Informationen finden Sie im Thema "Foreign Property" in-DAO-Hilfe.

*m_lDistinctCount*<br/>
Gibt die Anzahl der eindeutigen Werte für das Indexobjekt, die in der zugeordneten Tabelle enthalten sind. Überprüfen Sie die DistinctCount-Eigenschaft, um die Anzahl eindeutiger Werte oder Schlüssel in einem Index zu bestimmen. Eine beliebige Taste, wird nur einmal gezählt, auch wenn es mehrere Vorkommen von diesem Wert sein können, wenn der Index doppelte Werte zulässt. Diese Informationen sind nützlich bei Anwendungen, die versuchen, den Datenzugriff zu optimieren, indem Sie Ihre Evaluierung von Indexinformationen. Die Anzahl von eindeutigen Werten ist auch bekannt als die Kardinalität eines Index-Objekts. Die DistinctCount-Eigenschaft wird nicht immer die tatsächliche Anzahl der Schlüssel zu einem bestimmten Zeitpunkt wider. Beispielsweise wird eine Änderung durch ein Transaktionsrollback nicht sofort in der DistinctCount-Eigenschaft wiedergegeben werden. Weitere Informationen finden Sie im Thema "DistinctCount-Eigenschaft" in-DAO-Hilfe.

## <a name="remarks"></a>Hinweise

Die Verweise auf die primäre, sekundäre und alle oben angegeben, wie die Informationen zurückgegeben werden, indem die `GetIndexInfo` Memberfunktion in Klassen [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md#getindexinfo) und [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md#getindexinfo).

Index-Objekte werden nicht von einer MFC-Klasse dargestellt. Stattdessen DAO Objekten zugrunde liegenden MFC-Objekte der Klasse [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md) oder [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) enthalten eine Auflistung von indexobjekten, die der Indexsammlung aufgerufen. Diese Klassen geben Member-Funktionen für den Zugriff auf einzelne Elemente der Informationen zu Indizes an, oder darauf gleichzeitig mit zugreifen eine `CDaoIndexInfo` -Objekt durch Aufrufen der `GetIndexInfo` Memberfunktion Rand des enthaltenden Objekts.

`CDaoIndexInfo` verfügt über einen Konstruktor und einen Destruktor, um ordnungsgemäß reservieren und Freigeben von die Index-Feldinformationen in `m_pFieldInfos`.

Informationen, die abgerufen, indem die `GetIndexInfo` Memberfunktion eines Tabledef-Objekts befindet sich in einer `CDaoIndexInfo` Struktur. Rufen Sie die `GetIndexInfo` Memberfunktion das enthaltende Tabledef-Objekt, Index-Objekt wird in die Auflistung, deren Indizes gespeichert. `CDaoIndexInfo` definiert auch eine `Dump` -Memberfunktion im Debug-builds. Können Sie `Dump` zum Sichern den Inhalt einer `CDaoIndexInfo` Objekt.

## <a name="requirements"></a>Anforderungen

**Header:** afxdao.h

## <a name="see-also"></a>Siehe auch

[Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CDaoTableDef::GetIndexInfo](../../mfc/reference/cdaotabledef-class.md#getindexinfo)

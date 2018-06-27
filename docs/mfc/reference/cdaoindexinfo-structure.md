---
title: CDaoIndexInfo-Struktur | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CDaoIndexInfo
dev_langs:
- C++
helpviewer_keywords:
- DAO (Data Access Objects), Indexes collection
- CDaoIndexInfo structure [MFC]
ms.assetid: 251d8285-78ce-4716-a0b3-ccc3395fc437
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 85e59173ec330d0a5abb968225ce6b2e12263948
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/26/2018
ms.locfileid: "36954064"
---
# <a name="cdaoindexinfo-structure"></a>CDaoIndexInfo-Struktur
Die `CDaoIndexInfo` Struktur enthält Informationen zu einem Indexobjekt, das für Datenzugriffsobjekte (DAO) definiert.  
  
## <a name="syntax"></a>Syntax  
  
```  
struct CDaoIndexInfo {  
    CDaoIndexInfo();
*// Constructor  
    CString m_strName;  // Primary  
    CDaoIndexFieldInfo* m_pFieldInfos;  // Primary  
    short m_nFields;    // Primary  
    BOOL m_bPrimary;    // Secondary  
    BOOL m_bUnique;     // Secondary  
    BOOL m_bClustered;  // Secondary  
    BOOL m_bIgnoreNulls;                // Secondary  
    BOOL m_bRequired;   // Secondary  
    BOOL m_bForeign;    // Secondary  
    long m_lDistinctCount;              // All  
 *// Below the // Implementation comment: *// Destructor, not otherwise documented  
};   
```  
  
#### <a name="parameters"></a>Parameter  
 *m_strName*  
 Eindeutig benennt das Feldobjekt. Details finden Sie im Thema "Name-Eigenschaft" DAO-Hilfe.  
  
 *m_pFieldInfos*  
 Ein Zeiger auf ein Array von [CDaoIndexFieldInfo](../../mfc/reference/cdaoindexfieldinfo-structure.md) Objekte, der angibt, welche Tabledef oder ein Recordset-Felder in einem Index Schlüsselfelder sind. Jedes Objekt identifiziert ein Feld im Index. Der Index Standardreihenfolge ist Aufsteigend. Ein Indexobjekt kann ein oder mehrere Felder, die für jeden Datensatz Indexschlüssel darstellt haben. Diese können, absteigend, oder eine Kombination aufsteigend sortiert sein.  
  
 *m_nFields*  
 Die Anzahl der Felder, die in gespeicherten *M_pFieldInfos*.  
  
 *m_bPrimary*  
 Wenn die primäre Eigenschaft **"true"**, Index-Objekt stellt einen primären Index dar. Ein primärer Index besteht aus einem oder mehreren Feldern, die alle Datensätze in einer Tabelle in einer vordefinierten Reihenfolge eindeutig zu identifizieren. Da Indexfeld eindeutig sein muss, ist die Unique-Eigenschaft des Indexobjekts auch zum Festlegen **"true"** über DAO. Wenn es sich bei der Primärindex aus mehr als ein Feld besteht, kann jedes Feld doppelte Werte enthalten, aber jede Kombination von Werten aus den indizierten Feldern muss eindeutig sein. Ein primärer Index besteht aus einem Schlüssel für die Tabelle und in der Regel enthält die gleichen Felder als Primärschlüssel.  
  
 Wenn Sie einen Primärschlüssel für eine Tabelle festlegen, wird der Primärschlüssel automatisch als primären Index für die Tabelle definiert. Weitere Informationen finden Sie unter den Themen "Primäre-Eigenschaft" und "Eindeutige Eigenschaft" DAO-Hilfe.  
  
> [!NOTE]
>  Es kann sein, darf höchstens einen primären Index für eine Tabelle.  
  
 *m_bUnique*  
 Gibt an, ob ein Indexobjekt einen eindeutigen Index für eine Tabelle darstellt. Wenn diese Eigenschaft ist **"true"**, Index-Objekt stellt einen Index, der eindeutig ist. Ein eindeutiger Index besteht aus einem oder mehreren Feldern, die logisch alle Datensätze in einer Tabelle in einer eindeutigen, vordefinierten Reihenfolge anordnen. Wenn der Index der aus einem Feld besteht, müssen Werte im Feld für die gesamte Tabelle eindeutig sein. Wenn der Index von mehr als ein Feld besteht, kann jedes Feld doppelte Werte enthalten, aber jede Kombination von Werten aus den indizierten Feldern muss eindeutig sein.  
  
 Wenn die Unique- und die primären Eigenschaften eines Indexobjekts, um festgelegt werden **"true"**, der Index ist Unique- und primary: Es werden alle Datensätze in der Tabelle in einer vordefinierten, logischen Reihenfolge eindeutig identifiziert. Wenn die Eigenschaft für Primärschlüssel, um festgelegt ist **"false"**, der Index ist ein sekundärer Index. Sekundäre Indizes (sowohl wichtige als auch Nichtschlüsselspalten) ordnen Datensätze in einer vordefinierten Reihenfolge logisch ohne als Bezeichner für die Datensätze in der Tabelle zu dienen.  
  
 Weitere Informationen finden Sie unter den Themen "Primäre-Eigenschaft" und "Eindeutige Eigenschaft" DAO-Hilfe.  
  
 *m_bClustered*  
 Gibt an, ob ein Indexobjekt einen gruppierten Index für eine Tabelle darstellt. Wenn diese Eigenschaft ist **"true"**, Index-Objekt dar, einen gruppierten Index; hingegen nicht. Ein gruppierter Index besteht aus einer oder mehreren Nichtschlüsselfeldern, alle Datensätze in einer Tabelle in einer vordefinierten Reihenfolge anordnen zusammen. Mit einem gruppierten Index werden die Daten in der Tabelle wörtlich in der Reihenfolge angegeben, die vom gruppierten Index gespeichert. Ein gruppierter Index bietet effizienten Zugriff auf Datensätze in einer Tabelle. Weitere Informationen finden Sie im Thema "Clustered-Eigenschaft" DAO-Hilfe.  
  
> [!NOTE]
>  Die Clustered-Eigenschaft wird für Datenbanken ignoriert, die das Microsoft Jet-Datenbankmodul verwenden, da das Jet-Datenbankmodul nicht gruppierten Indizes unterstützt.  
  
 *m_bIgnoreNulls*  
 Gibt an, ob der Indexeinträge für Datensätze mit Null-Werte in ihren Indexfelder vorhanden sind. Wenn diese Eigenschaft ist **"true"**, Felder mit Null-Werten müssen keine Indexeintrag. Zum Suchen nach Datensätzen, die mithilfe eines Felds schneller zu machen, können Sie einen Index für das Feld definieren. Wenn Sie Null-Einträge in einer indizierten Felds zulassen und erwarten, dass viele Einträge Null sein kann, legen Sie die IgnoreNulls-Eigenschaft für das Indexobjekt, das **"true"** um den Speicherplatz zu reduzieren, die den Index verwendet. Die Einstellung der Eigenschaft IgnoreNulls und die erforderliche eigenschafteneinstellung bestimmen zusammen, ob ein Datensatz mit einem Null-Indexwert Indexeintrag, wie in der folgenden Tabelle gezeigt wurde.  
  
|IgnoreNulls|Erforderlich|NULL im Feld "Index"|  
|-----------------|--------------|-------------------------|  
|True|False|NULL-Wert zulässig; keine Indexeintrag hinzugefügt.|  
|False|False|NULL-Wert zulässig; der Indexeintrag hinzugefügt.|  
|True oder False|True|NULL-Wert nicht zulässig; keine Indexeintrag hinzugefügt.|  
  
 Weitere Informationen finden Sie im Thema "IgnoreNulls-Eigenschaft" DAO-Hilfe.  
  
 *m_bRequired*  
 Gibt an, ob ein DAO-Index-Objekt einen Wert ungleich Null erfordert. Wenn diese Eigenschaft ist **"true"**, das Indexobjekt lässt sich nicht auf einen Null-Wert. Weitere Informationen finden Sie im Thema "Erforderliche Eigenschaft" DAO-Hilfe.  
  
> [!TIP]
>  Beim Festlegen dieser Eigenschaft für ein DAO-Index-Objekt oder ein Field-Objekt (durch eine Tabledef, Recordset oder DAO Querydef-Objekt enthalten) legen Sie sie für die Field-Objekt. Die Gültigkeit der Einstellung der Eigenschaft für ein Field-Objekt wird überprüft, bevor, eines Index-Objekts.  
  
 *m_bForeign*  
 Gibt an, ob ein Indexobjekt einen Fremdschlüssel in einer Tabelle darstellt. Wenn diese Eigenschaft ist **"true"**, den Index darstellt, einen Fremdschlüssel in einer Tabelle. Ein Fremdschlüssel besteht aus ein oder mehrere Felder in einer Fremdschlüsseltabelle, die eine Zeile in einer primären Tabelle eindeutig identifizieren. Das Microsoft Jet-Datenbankmodul für die Fremdschlüsseltabelle ein Indexobjekt erstellt und die Fremdschlüssel-Eigenschaft legt fest, wenn Sie eine Beziehung erstellen, die referenzielle Integrität gewährleistet. Weitere Informationen finden Sie im Thema "Foreign Property" in der DAO-Hilfe.  
  
 *m_lDistinctCount*  
 Gibt die Anzahl der eindeutigen Werte für das Indexobjekt, die in der zugeordneten Tabelle enthalten sind. Überprüfen Sie die DistinctCount-Eigenschaft zum Bestimmen der Anzahl von eindeutigen Werten oder Schlüsseln, in einem Index. Eine beliebige Taste, wird nur einmal gezählt werden, obwohl es mehrere Vorkommen des entsprechenden Wertes sein kann, wenn der Index doppelte Werte zulässt. Diese Informationen sind hilfreich in Anwendungen, die versuchen, Zugriff auf Daten durch das Auswerten von Indexinformationen zu optimieren. Die Anzahl der eindeutigen Werte ist auch bekannt als die Kardinalität eines Index-Objekts. Die DistinctCount-Eigenschaft wird nicht immer entsprechend der tatsächlichen Anzahl von Schlüsseln zu einem bestimmten Zeitpunkt. Beispielsweise wird eine Änderung durch ein Transaktionsrollback nicht sofort in der DistinctCount-Eigenschaft wiedergegeben werden. Weitere Informationen finden Sie im Thema "DistinctCount-Eigenschaft" DAO-Hilfe.  
  
## <a name="remarks"></a>Hinweise  
 Die Verweise auf die primäre, sekundäre Datenbank und alle oben anzugeben, wie die Informationen zurückgegeben werden, durch die `GetIndexInfo` Memberfunktion in Klassen [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md#getindexinfo) und [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md#getindexinfo).  
  
 Index-Objekte werden nicht von einer MFC-Klasse dargestellt. Stattdessen DAO Objekten zugrunde liegenden MFC-Objekte der Klasse [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md) oder [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) eine Auflistung von indexobjekten, bezeichnet die Auflistung von Indizes enthalten. Diese Klassen geben Memberfunktionen für den Zugriff auf einzelne Elemente von Indexinformationen, oder Sie auf Sie zugreifen können alle gleichzeitig mit einem `CDaoIndexInfo` Objekt durch Aufrufen der `GetIndexInfo` Memberfunktion Rand des enthaltenden Objekts.  
  
 `CDaoIndexInfo` verfügt über einen Konstruktor und einen Destruktor, um ordnungsgemäß zuordnen und Aufheben der Zuordnung der Feldinformationen Index in *M_pFieldInfos*.  
  
 Informationen, die abgerufen, indem die `GetIndexInfo` Memberfunktion eines Objekts Tabledef befindet sich in einer `CDaoIndexInfo` Struktur. Rufen Sie die `GetIndexInfo` Memberfunktion Rand des enthaltenden Tabledef-Objekts, das in die Auflistung, deren Indizes das Indexobjekt gespeichert ist. `CDaoIndexInfo` definiert auch einen `Dump` Memberfunktion in Debug-builds. Sie können `Dump` auf den Inhalt des Basisklassenobjekts auszugeben ein `CDaoIndexInfo` Objekt.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxdao.h  
  
## <a name="see-also"></a>Siehe auch  
 [Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDaoTableDef::GetIndexInfo](../../mfc/reference/cdaotabledef-class.md#getindexinfo)


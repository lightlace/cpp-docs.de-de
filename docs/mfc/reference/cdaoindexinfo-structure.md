---
title: CDaoIndexInfo-Struktur | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CDaoIndexInfo
dev_langs:
- C++
helpviewer_keywords:
- DAO (Data Access Objects), Indexes collection
- CDaoIndexInfo structure
ms.assetid: 251d8285-78ce-4716-a0b3-ccc3395fc437
caps.latest.revision: 13
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 92206d8d8f9b2315fb859e2712a83d32a4c293ad
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

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
 `m_strName`  
 Field-Objekt bezeichnet eindeutig. Details finden Sie im Thema "Name-Eigenschaft" in der DAO-Hilfe.  
  
 `m_pFieldInfos`  
 Ein Zeiger auf ein Array von [CDaoIndexFieldInfo](../../mfc/reference/cdaoindexfieldinfo-structure.md) Objekte, der angibt, welche Felder Tabledef oder DAO-Recordsets Felder in einem Index sind. Jedes Objekt identifiziert ein Feld im Index. Index Standardreihenfolge ist Aufsteigend. Ein Index-Objekt können ein oder mehrere Felder, Indexschlüssel für jeden Datensatz darstellt. Diese können, absteigend, oder eine Kombination Aufsteigend.  
  
 `m_nFields`  
 Die Anzahl der Felder, die in gespeicherten `m_pFieldInfos`.  
  
 *m_bPrimary*  
 Wenn die primäre Eigenschaft ist **TRUE**, Index-Objekt stellt einen primären Index dar. Ein primärer Index besteht aus einem oder mehreren Feldern, die alle Datensätze in einer Tabelle in einer vordefinierten Reihenfolge eindeutig zu identifizieren. Da Indexfeld eindeutig sein muss, ist die Unique-Eigenschaft des Index-Objekts auch zum Festlegen **TRUE** in DAO. Wenn der primäre Index aus mehr als einem Feld besteht, kann jedes Feld doppelte Werte enthalten, aber jede Kombination der Werte aller indizierten Felder muss eindeutig sein. Ein primärer Index besteht aus einem Schlüssel für die Tabelle und in der Regel enthält die gleichen Felder als Primärschlüssel.  
  
 Wenn Sie einen Primärschlüssel für eine Tabelle festlegen, wird der Primärschlüssel automatisch als der primäre Index für die Tabelle definiert. Weitere Informationen finden Sie unter den Themen "Primäre Property" und "Unique-Eigenschaft" in der DAO-Hilfe.  
  
> [!NOTE]
>  Vorhanden sein können, höchstens über einen primären Index für eine Tabelle.  
  
 *m_bUnique*  
 Gibt an, ob ein Indexobjekt einen eindeutigen Index für eine Tabelle darstellt. Wenn diese Eigenschaft ist **TRUE**, Index-Objekt stellt einen Index, der eindeutig ist. Ein eindeutiger Index besteht aus einem oder mehreren Feldern, die alle Datensätze in einer Tabelle in einer eindeutigen, vordefinierten Reihenfolge logisch anordnen. Wenn der Index aus einem Feld besteht, müssen Werte für die gesamte Tabelle eindeutig sein. Wenn der Index aus mehreren Feldern besteht, kann jedes Feld doppelte Werte enthalten, aber jede Kombination der Werte aller indizierten Felder muss eindeutig sein.  
  
 Wenn die Unique- und die primären eines Index-Objekts Eigenschaften **TRUE**, der Index ist eindeutig und primär: Es werden alle Datensätze in der Tabelle in einer vordefinierten, logischen Reihenfolge eindeutig identifiziert. Wenn die Primärschlüssel-Eigenschaft, um festgelegt wird **FALSE**, der Index ist ein sekundärer Index. Sekundäre Indizes (mit und ohne Schlüssel) ordnen Datensätze logisch in einer vordefinierten Reihenfolge ohne als Bezeichner für Datensätze in der Tabelle zu dienen.  
  
 Weitere Informationen finden Sie unter den Themen "Primäre Property" und "Unique-Eigenschaft" in der DAO-Hilfe.  
  
 *m_bClustered*  
 Gibt an, ob ein Index-Objekt einen gruppierten Index für eine Tabelle darstellt. Wenn diese Eigenschaft ist **TRUE**, Index-Objekt stellt einen gruppierten Index; andernfalls nicht. Ein gruppierter Index besteht aus einem oder mehreren Nichtschlüsselfeldern, die zusammen genommen alle Datensätze in einer Tabelle in einer vordefinierten Reihenfolge anordnen. Mit einem gruppierten Index werden die Daten in der Tabelle wörtlich in der Reihenfolge angegeben werden, indem der gruppierte Index gespeichert. Ein gruppierter Index bietet effizienten Zugriff auf Datensätze in einer Tabelle. Weitere Informationen finden Sie unter dem Thema "Clustered-Eigenschaft" DAO-Hilfe.  
  
> [!NOTE]
>  Die Clustered-Eigenschaft wird für Datenbanken ignoriert, die das Microsoft Jet-Datenbankmodul verwenden, da das Jet-Datenbankmodul keine gruppierten Indizes unterstützt.  
  
 *m_bIgnoreNulls*  
 Gibt an, ob es werden Indexeinträge für Datensätze, die Null-Werte in den Indexfeldern haben. Wenn diese Eigenschaft ist **TRUE**, Felder mit Null-Werten haben keinen Indexeintrag. Um die Suche nach Datensätzen, die mit einem Feld schneller zu machen, können Sie einen Index für das Feld definieren. Wenn Sie Null-Einträge in einem indizierten Feld zulassen und erwarten, viele Einträge dass den Wert Null haben, können Sie festlegen, dass die IgnoreNulls-Eigenschaft für das Indexobjekt, das **TRUE** Speicherplatz reduzieren, die der Index verwendet. Die IgnoreNulls-Eigenschaft und der Einstellung für die erforderliche Eigenschaft bestimmen zusammen, ob ein Datensatz mit einem Null-Indexwert die folgende Tabelle zeigt einen Indexeintrag verfügt.  
  
|IgnoreNulls|Erforderlich|NULL-Index-Feld|  
|-----------------|--------------|-------------------------|  
|True|False|NULL-Wert zulässig; Es wird kein Indexeintrag hinzugefügt.|  
|False|False|NULL-Wert zulässig; Indexeintrag hinzugefügt.|  
|True oder False|True|NULL-Wert nicht zulässig; Es wird kein Indexeintrag hinzugefügt.|  
  
 Weitere Informationen finden Sie unter dem Thema "IgnoreNulls-Eigenschaft" in der DAO-Hilfe.  
  
 `m_bRequired`  
 Gibt an, ob ein DAO-Index-Objekt einen Wert ungleich Null erfordert. Wenn diese Eigenschaft ist **TRUE**, Indexobjekt lässt sich nicht auf einen Null-Wert. Weitere Informationen finden Sie unter dem Thema "Erforderliche Eigenschaft" DAO-Hilfe.  
  
> [!TIP]
>  Wenn Sie diese Eigenschaft für ein DAO-Index-Objekt oder ein Field-Objekt (eine Tabledef, Recordset oder ein Querydef-Objekt enthalten) festlegen können, legen Sie sie für das Field-Objekt. Die Gültigkeit der Einstellung der Eigenschaft für ein Field-Objekt wird überprüft, bevor der Index-Objekts.  
  
 *m_bForeign*  
 Gibt an, ob ein Indexobjekt einen Fremdschlüssel in einer Tabelle darstellt. Wenn diese Eigenschaft ist **TRUE**, der Index einen Fremdschlüssel in einer Tabelle darstellt. Ein Fremdschlüssel besteht aus einem oder mehreren Feldern in einer Fremdtabelle, die eine Zeile in einer primären Tabelle eindeutig identifizieren. Das Microsoft Jet-Datenbankmodul erstellt ein Indexobjekt für die Fremdtabelle und legt die Foreign-Eigenschaft, wenn Sie eine Beziehung erstellen, die referenzielle Integrität gewährleistet. Weitere Informationen finden Sie unter dem Thema "Foreign-Eigenschaft" in der DAO-Hilfe.  
  
 *m_lDistinctCount*  
 Gibt die Anzahl der eindeutigen Werte für die Index-Objekt, die in der zugeordneten Tabelle enthalten sind. Überprüfen Sie die DistinctCount-Eigenschaft zum Ermitteln der Anzahl von eindeutigen Werten oder Schlüsseln in einem Index. Eine beliebige Taste wird nur einmal gezählt, obwohl es möglicherweise mehrere Vorkommen dieses Werts sein, wenn der Index doppelte Werte zulässt. Diese Informationen sind nützlich, die versuchen, Zugriff auf Daten durch das Auswerten von Indexinformationen zu optimieren. Die Anzahl von eindeutigen Werten wird auch die Kardinalität des Index-Objekts. Die DistinctCount-Eigenschaft wider nicht immer die tatsächliche Anzahl von Schlüsseln zu einem bestimmten Zeitpunkt. Beispielsweise wird eine Änderung durch ein Transaktionsrollback nicht sofort in der DistinctCount-Eigenschaft wiedergegeben werden. Weitere Informationen finden Sie unter dem Thema "DistinctCount-Eigenschaft" in der DAO-Hilfe.  
  
## <a name="remarks"></a>Hinweise  
 Die Verweise auf die primären, sekundären und alle oben anzugeben, wie die Informationen zurückgegeben werden, durch die `GetIndexInfo` -Memberfunktion in Klassen [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md#getindexinfo) und [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md#getindexinfo).  
  
 Index-Objekte werden nicht von einer MFC-Klasse dargestellt. Stattdessen DAO Objekten zugrunde liegenden MFC-Objekte der Klasse [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md) oder [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) enthalten eine Auflistung von indexobjekten, die die Auflistung von Indizes aufgerufen. Diese Klassen Memberfunktionen für den Zugriff auf einzelne Elemente von Indexinformationen oder können sie gleichzeitig mit zugreifen ein `CDaoIndexInfo` -Objekt durch Aufrufen der `GetIndexInfo` -Memberfunktion des enthaltenden Objekts.  
  
 `CDaoIndexInfo`verfügt über einen Konstruktor und Destruktor um ordnungsgemäß reservieren und Freigeben von den Index Feldinformationen in `m_pFieldInfos`.  
  
 Informationen abgerufen werden, indem Sie die `GetIndexInfo` -Memberfunktion des Tabledef-Objekts befindet sich in einer `CDaoIndexInfo` Struktur. Rufen Sie die `GetIndexInfo` -Memberfunktion des enthaltenden Tabledef-Objekts, das in die Auflistung, deren Indizes die Indexobjekt gespeichert ist. `CDaoIndexInfo`definiert auch eine `Dump` Memberfunktion im Debugmodus erstellt. Sie können `Dump` auf den Inhalt des Basisklassenobjekts auszugeben ein `CDaoIndexInfo` Objekt.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxdao.h  
  
## <a name="see-also"></a>Siehe auch  
 [Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDaoTableDef::GetIndexInfo](../../mfc/reference/cdaotabledef-class.md#getindexinfo)



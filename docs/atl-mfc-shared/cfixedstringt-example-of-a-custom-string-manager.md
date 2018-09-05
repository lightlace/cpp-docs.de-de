---
title: 'CFixedStringT: Beispiel eines benutzerdefinierten Zeichenfolgenmanagers | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- CFixedStringT class, using a custom string manager
ms.assetid: 1cf11fd7-51b8-4b94-87af-02bc25f47dd6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9f16bc5a9357199a5c5113fd33a62467d63e4f1d
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2018
ms.locfileid: "43768033"
---
# <a name="cfixedstringt-example-of-a-custom-string-manager"></a>CFixedStringT: Beispiel eines benutzerdefinierten Zeichenfolgenmanagers

Die ATL-Bibliothek implementiert ein Beispiel eines benutzerdefinierten zeichenfolgenmanagers von Klasse verwendeten [CFixedStringT](../atl-mfc-shared/reference/cfixedstringt-class.md)namens **CFixedStringMgr**. `CFixedStringT` stammt aus [CStringT](../atl-mfc-shared/reference/cstringt-class.md) und implementiert eine Zeichenfolge, die die Zeichendaten als Teil des weist die `CFixedStringT` Objekt selbst, solange die Zeichenfolge, die kleiner als die Länge von angegeben ist die `t_nChars` Template-Parameter der `CFixedStringT`. Bei diesem Ansatz ist die Zeichenfolge nicht den Heap, erforderlich, wenn die Größe der Puffer mit fester Größe die Länge der Zeichenfolge überschreitet. Da `CFixedStringT` ist nicht immer mit einen Heap Zuweisen der Zeichenfolgendaten, es können keine `CAtlStringMgr` als Zeichenfolgen-Manager. Er verwendet einen benutzerdefinierten zeichenfolgenmanagers (`CFixedStringMgr`), implementieren die [IAtlStringMgr](../atl-mfc-shared/reference/iatlstringmgr-class.md) Schnittstelle. Diese Schnittstelle wird im erläutert [Implementierung eines benutzerdefinierten Zeichenfolgenmanagers (Advanced-Methode)](../atl-mfc-shared/implementation-of-a-custom-string-manager-advanced-method.md).

Der Konstruktor für `CFixedStringMgr` akzeptiert drei Parameter:

- *pData:* einen Zeiger an den festen `CStringData` Struktur verwendet werden.

- *nChars:* die maximale Anzahl von Zeichen der `CStringData` Struktur enthalten kann.

- *pMgr:* ein Zeiger auf die `IAtlStringMgr` Schnittstelle "backup Zeichenfolge Manager".

Der Konstruktor speichert die Werte der *pData* und *pMgr* in den entsprechenden Membervariablen (`m_pData` und `m_pMgr`). Klicken Sie dann festgelegt die Länge des Puffers zum gleich NULL ist, werden die verfügbaren Länge gleich der maximalen Größe der Puffer mit fester Größe, und der Verweiszähler auf-1. Die Verweisanzahl den Wert gibt an, der Puffer ist gesperrt, und verwenden diese Instanz von `CFixedStringMgr` als Zeichenfolge-Manager.

Markieren den Puffer als gesperrt wird verhindert, dass andere `CStringT` Instanzen von gemeinsam genutzten verweisen auf den Puffer. Wenn andere `CStringT` Instanzen wurden zulässig, den Puffer zu nutzen, es möglich, für den Puffer enthaltenen wäre `CFixedStringT` gelöscht werden, während andere Zeichenfolgen weiterhin den Puffer verwendet haben.

`CFixedStringMgr` ist eine vollständige Implementierung der `IAtlStringMgr` Schnittstelle. Die Implementierung der einzelnen Methoden werden separat erläutert.

## <a name="implementation-of-cfixedstringmgrallocate"></a>Implementierung von CFixedStringMgr:: Allocate

Die Implementierung der `CFixedStringMgr::Allocate` prüft zunächst, ob die angeforderte Größe der Zeichenfolge kleiner oder gleich der Größe der Puffer mit fester Größe ist (gespeichert der `m_pData` Member). Wenn der Puffer mit feste Größe groß genug ist `CFixedStringMgr` sperrt Puffer mit festen Größe mit einer Länge von 0 (null). Als die Länge der Zeichenfolge nicht über die Größe der Puffer mit fester Größe, wächst `CStringT` müssen keinen Puffer zum erneuten zuweisen.

Wenn die angeforderte Größe der Zeichenfolge größer als der Puffer mit fester Größe ist `CFixedStringMgr` leitet die Anforderung an dem Manager für die Sicherung Zeichenfolge. Die Sicherung zeichenfolgenmanagers wird davon ausgegangen, dass den Puffer aus dem Heap reserviert werden. Jedoch vor der Rückgabe dieses Puffers `CFixedStringMgr` Sperren des Puffers und ersetzt die Puffer-Manager-Zeichenfolgenzeiger mit einem Zeiger auf die `CFixedStringMgr` Objekt. Dadurch wird sichergestellt, der versucht, zuordnen oder Freigeben des Puffers von `CStringT` aufrufen wird `CFixedStringMgr`.

## <a name="implementation-of-cfixedstringmgrreallocate"></a>Implementierung von CFixedStringMgr::ReAllocate

Die Implementierung der `CFixedStringMgr::ReAllocate` ist sehr ähnlich zu seiner Implementierung von `Allocate`.

Wenn der Puffer, der neu zugeordnet, den Puffer mit fester Größe ist, und die angeforderten Puffergröße kleiner als der Puffer mit fester Größe ist, erfolgt keine Zuweisung. Wenn der Puffer, der neu zugeordnet, die nicht Puffer mit fester Größe ist, muss es jedoch einen Puffer mit der backup-Manager zugeordnet sein. In diesem Fall wird der backup-Manager verwendet, den Puffer zu nutzen.

Wenn der Puffer, der neu zugeordnet, den Puffer mit fester Größe ist und die neue Puffergröße zu groß ist für die in den Puffer mit fester Größe, passen `CFixedStringMgr` weist einen neuen Puffer mithilfe des backup-Managers. Den Inhalt der Puffer mit fester Größe werden dann in den neuen Puffer kopiert werden.

## <a name="implementation-of-cfixedstringmgrfree"></a>Implementierung von FixedStringMgr

Die Implementierung der `CFixedStringMgr::Free` folgt demselben Muster wie `Allocate` und `ReAllocate`. Wenn der Puffer, der freigegeben Puffer mit fester Größe ist, wird die Methode auf ein gesperrter Puffer der Länge 0 (null). Wenn der Puffer wird mit der backup-Manager, belegt wurde `CFixedStringMgr` verwendet den backup-Manager die Freigabe.

## <a name="implementation-of-cfixedstringmgrclone"></a>Implementierung von CFixedStringMgr::Clone

Die Implementierung der `CFixedStringMgr::Clone` stets einen Zeiger auf den backup-Manager zurück statt der `CFixedStringMgr` selbst. Dies liegt daran, dass jede Instanz des `CFixedStringMgr` kann nur eine einzelne Instanz zugeordnet werden `CStringT`. Alle anderen Instanzen der `CStringT` möchten, Klonen Sie den Manager erhalten die Sicherungen-Manager. stattdessen. Dies ist, da der backup-Manager unterstützt freigegeben.

## <a name="implementation-of-cfixedstringmgrgetnilstring"></a>Implementierung von CFixedStringMgr::GetNilString

Die Implementierung der `CFixedStringMgr::GetNilString` gibt Puffer mit festen Größe. Aufgrund der direkten Entsprechung der `CFixedStringMgr` und `CStringT`, eine bestimmte Instanz der `CStringT` nie mehr als einen Puffer zu einem Zeitpunkt verwendet. Aus diesem Grund sind eine NULL-Zeichenfolge und einen echten Zeichenfolgenpuffer nie zur gleichen Zeit erforderlich.

Wenn der Puffer mit feste Größe nicht verwendet werden, ist `CFixedStringMgr` wird sichergestellt, dass es mit einer Länge von 0 (null) initialisiert wird. Dadurch kann er als die NULL-Zeichenfolge verwendet werden soll. Als zusätzlichen Bonus der `nAllocLength` Mitglied Puffer mit fester Größe ist immer auf voller Größe der Puffer mit fester Größe festgelegt. Dies bedeutet, dass `CStringT` anwachsen kann die Zeichenfolge ohne [IAtlStringMgr::Reallocate](../atl-mfc-shared/reference/iatlstringmgr-class.md#reallocate), dies gilt auch für die NULL-Zeichenfolge.

## <a name="requirements"></a>Anforderungen

**Header:** cstringt.h

## <a name="see-also"></a>Siehe auch

[Speicherverwaltung mit CStringT](../atl-mfc-shared/memory-management-with-cstringt.md)


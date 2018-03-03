---
title: 'CFixedStringT: Beispiel eines benutzerdefinierten Zeichenfolge-Managers | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- CFixedStringT class, using a custom string manager
ms.assetid: 1cf11fd7-51b8-4b94-87af-02bc25f47dd6
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7164d2313f5610d1d7e56f5449c81ea9e2282981
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="cfixedstringt-example-of-a-custom-string-manager"></a>CFixedStringT: Beispiel eines benutzerdefinierten Zeichenfolge-Managers
ATL-Bibliothek implementiert ein Beispiel für eine benutzerdefinierte Zeichenfolge-Manager, die von Klasse verwendeten [CFixedStringT](../atl-mfc-shared/reference/cfixedstringt-class.md)namens **CFixedStringMgr**. `CFixedStringT`stammt aus [CStringT](../atl-mfc-shared/reference/cstringt-class.md) und implementiert eine Zeichenfolge, die als Teil seiner Zeichendaten ordnet die `CFixedStringT` Objekt selbst, solange die Zeichenfolge kleiner als die Länge ist der **T_nChars** der Vorlagenparameter `CFixedStringT`. Bei diesem Ansatz ist die Zeichenfolge nicht im Heap überhaupt erforderlich, wenn die Größe des Puffers fester Größe die Länge der Zeichenfolge überschreitet. Da `CFixedStringT` verwendet nicht immer einen Heap Zuweisen der Zeichenfolgendaten, es können keine **CAtlStringMgr** als Zeichenfolgen-Manager. Er verwendet einen benutzerdefinierte Zeichenfolge-Manager (**CFixedStringMgr**), implementieren die [IAtlStringMgr](../atl-mfc-shared/reference/iatlstringmgr-class.md) Schnittstelle. Diese Schnittstelle wird erläutert, [Implementierung eines benutzerdefinierten Zeichenfolge-Managers (Advanced-Methode)](../atl-mfc-shared/implementation-of-a-custom-string-manager-advanced-method.md).  
  
 Der Konstruktor für **CFixedStringMgr** akzeptiert drei Parameter:  
  
-   **pData:** ein Zeiger auf die feste `CStringData` Struktur verwendet werden.  
  
-   **nChars:** die maximale Anzahl von Zeichen der `CStringData` Struktur aufnehmen kann.  
  
-   **pMgr:** ein Zeiger auf die `IAtlStringMgr` Schnittstelle eines "backup Zeichenfolge-Managers."  
  
 Der Konstruktor speichert die Werte von `pData` und **pMgr** in den entsprechenden Membervariablen (`m_pData` und **M_pMgr**). Anschließend wird die Länge des Puffers auf 0 (null), die verfügbar Länge gleich der maximalen Größe der Puffer mit fester Größe und den Verweiszähler auf-1 festgelegt. Gibt die Verweisanzahl den Wert an der Puffer ist gesperrt und verwenden diese Instanz von **CFixedStringMgr** als Zeichenfolgen-Manager.  
  
 Den Puffer als gesperrt markiert wird verhindert, dass andere `CStringT` Instanzen über einen gemeinsamen Verweis auf den Puffer. Wenn andere `CStringT` Instanzen wurden dürfen Puffer gemeinsam verwenden, es, für den Puffer enthaltenen möglich ist `CFixedStringT` gelöscht werden, während andere Zeichenfolgen weiterhin den Puffer verwendet haben.  
  
 **CFixedStringMgr** ist eine vollständige Implementierung der `IAtlStringMgr` Schnittstelle. Die Implementierung der einzelnen Methoden wird separat erläutert.  
  
## <a name="implementation-of-cfixedstringmgrallocate"></a>Implementierung von CFixedStringMgr:: Allocate  
 Die Implementierung der **CFixedStringMgr:: Allocate** prüft zunächst, um festzustellen, ob die angeforderte Größe der Zeichenfolge kleiner oder gleich der Größe der Puffer mit fester Größe (gespeichert der `m_pData` Member). Wenn der Puffer mit feste Größe groß genug ist **CFixedStringMgr** sperrt Puffer mit festen Größe mit einer Länge von 0 (null). Solange die Länge der Zeichenfolge nicht über die Größe der Puffer mit fester Größe, wächst `CStringT` keine Puffer neu zuordnen.  
  
 Wenn die angeforderte Größe der Zeichenfolge größer als die Puffer mit fester Größe ist **CFixedStringMgr** leitet die Anforderung an dem Manager backup Zeichenfolge. Backup Zeichenfolgen-Manager wird davon ausgegangen, dass die Puffer aus dem Heap reserviert. Jedoch vor der Rückgabe dieser Puffer **CFixedStringMgr** sperrt den Puffer und ersetzt den Puffer-Manager Zeichenfolgenzeiger mit einem Zeiger auf die **CFixedStringMgr** Objekt. Dadurch wird sichergestellt, die versucht, zuordnen oder Freigeben des Puffers von `CStringT` angerufen in **CFixedStringMgr**.  
  
## <a name="implementation-of-cfixedstringmgrreallocate"></a>Implementierung von CFixedStringMgr::ReAllocate  
 Die Implementierung der **CFixedStringMgr::ReAllocate** ist vergleichbar mit der Implementierung der **Allocate**.  
  
 Wenn der Puffer zugewiesen wird der Puffer mit fester Größe und die angeforderten Puffergröße kleiner als die Puffer mit fester Größe ist, erfolgt keine Zuweisung. Allerdings muss ein Puffer zugewiesen wird, nicht Puffer mit fester Größe ist, einen Puffer mit der backup-Manager zugeordnet sein. In diesem Fall wird der backup-Manager verwendet, um den Puffer neu zu reservieren.  
  
 Wenn der Puffer zugewiesen wird der Puffer mit fester Größe und die neue Größe des Puffers zu groß ist für Puffer mit fester Größe, **CFixedStringMgr** einen neuen Puffer mit dem backup-Manager. Der Inhalt der Puffer mit fester Größe werden dann in den neuen Puffer kopiert werden.  
  
## <a name="implementation-of-cfixedstringmgrfree"></a>Implementierung von FixedStringMgr  
 Die Implementierung der **FixedStringMgr** folgt demselben Muster als **Allocate** und `ReAllocate`. Wenn der Puffer, der freigegeben wird der Puffer mit fester Größe ist, wird die Methode auf ein gesperrtes mit der Länge NULL-Puffer. Wenn der Puffer, der freigegeben wird mit dem backup-Manager zugewiesen wurde **CFixedStringMgr** verwendet den backup-Manager, um ihn freizugeben.  
  
## <a name="implementation-of-cfixedstringmgrclone"></a>Implementierung von CFixedStringMgr::Clone  
 Die Implementierung der **CFixedStringMgr::Clone** gibt immer einen Zeiger auf den backup-Manager anstelle des **CFixedStringMgr** selbst. Dies liegt daran, dass jede Instanz des **CFixedStringMgr** kann nur eine einzelne Instanz zugeordnet werden `CStringT`. Alle anderen Instanzen des `CStringT` bei dem Versuch, den Manager Klonen sollten abrufen den backup-Manager stattdessen. Dies ist, da der backup-Manager unterstützt wiederverwendet wird.  
  
## <a name="implementation-of-cfixedstringmgrgetnilstring"></a>Implementierung von CFixedStringMgr::GetNilString  
 Die Implementierung der **CFixedStringMgr::GetNilString** gibt Puffer mit festen Größe zurück. Aufgrund der Zweiergespräch Entsprechung der **CFixedStringMgr** und `CStringT`, eine bestimmte Instanz des `CStringT` nie mehr als einen Puffer zu einem Zeitpunkt verwendet. Aus diesem Grund sind eine NULL-Zeichenfolge und einen echten Zeichenfolgenpuffer nie zur gleichen Zeit erforderlich.  
  
 Wenn der Puffer mit feste Größe nicht verwendet, wird **CFixedStringMgr** wird sichergestellt, dass es mit der Länge 0 (null) initialisiert wird. Dadurch können sie mit der NULL-Zeichenfolge verwendet werden kann. Als ein weiterer Vorteil der `nAllocLength` Mitglied Puffer mit fester Größe ist immer auf die volle Größe des Puffer mit fester Größe festgelegt. Dies bedeutet, dass `CStringT` anwachsen kann die Zeichenfolge ohne Aufruf [IAtlStringMgr::Reallocate](../atl-mfc-shared/reference/iatlstringmgr-class.md#reallocate), dies gilt auch für die NULL-Zeichenfolge.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** cstringt.h  
  
## <a name="see-also"></a>Siehe auch  
 [Speicherverwaltung mit CStringT](../atl-mfc-shared/memory-management-with-cstringt.md)


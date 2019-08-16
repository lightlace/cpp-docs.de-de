---
title: Implementierung eines benutzerdefinierten Zeichen folgen-Managers (Basic-Methode)
ms.date: 11/04/2016
helpviewer_keywords:
- IAtlStringMgr class, using
ms.assetid: eac5d13e-cbb4-4e82-b01e-f5f2dbcb962a
ms.openlocfilehash: 92c1c46f5251980f9cefb55e052e9aff395e0e60
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69491317"
---
# <a name="implementation-of-a-custom-string-manager-basic-method"></a>Implementierung eines benutzerdefinierten Zeichen folgen-Managers (Basic-Methode)

Die einfachste Möglichkeit, das Speicher Belegungs Schema für Zeichen folgen Daten anzupassen, besteht darin, die von `CAtlStringMgr` ATL bereitgestellte Klasse zu verwenden, aber eigene Speicher Belegungs Routinen bereitzustellen. Der Konstruktor für `CAtlStringMgr` nimmt einen einzelnen Parameter an: einen Zeiger auf `IAtlMemMgr` ein Objekt. `IAtlMemMgr`ist eine abstrakte Basisklasse, die eine generische Schnittstelle für einen Heap bereitstellt. Mithilfe der `IAtlMemMgr` -Schnittstelle `CAtlStringMgr` wird der Arbeitsspeicher, der zum Speichern von Zeichen folgen Daten verwendet wird, zugeordnet, neu zugeordnet und freigegeben. Sie können entweder die `IAtlMemMgr` -Schnittstelle selbst implementieren oder eine der fünf vom ATL bereitgestellten Speicher-Manager-Klassen verwenden. Die von ATL bereitgestellten Speicher-Manager schließen einfach vorhandene Speicher Belegungs Funktionen ein:

- [Ccrtheiap](../atl/reference/ccrtheap-class.md) Umschließt die standardcrt-Heap Funktionen ([malloc](../c-runtime-library/reference/malloc.md), [Free](../c-runtime-library/reference/free.md)und [rezuweisung](../c-runtime-library/reference/realloc.md)).

- [CWin32Heap](../atl/reference/cwin32heap-class.md) Umschließt ein Win32-Heap Handle mithilfe von [Heapzuweisung](/windows/win32/api/heapapi/nf-heapapi-heapalloc), [HeapFree](/windows/win32/api/heapapi/nf-heapapi-heapfree)und [heaprezuweisung](/windows/win32/api/heapapi/nf-heapapi-heaprealloc) .

- [Clocalheap](../atl/reference/clocalheap-class.md) Umschließt die Win32-APIs: [Localzuweisung](/windows/win32/api/winbase/nf-winbase-localalloc), [LocalFree](/windows/win32/api/winbase/nf-winbase-localfree)und [localrezuweisungen](/windows/win32/api/winbase/nf-winbase-localrealloc)

- [Cglobalheap](../atl/reference/cglobalheap-class.md) Umschließt die Win32-APIs: [Globalzugewiesenen](/windows/win32/api/winbase/nf-winbase-globalalloc), [GlobalFree](/windows/win32/api/winbase/nf-winbase-globalfree)und [globalrezuweisungen](/windows/win32/api/winbase/nf-winbase-globalrealloc).

- [CComHeap](../atl/reference/ccomheap-class.md) Umschließt die com-Task zuordnerapis: [Cotaskmemzuweisung](/windows/win32/api/combaseapi/nf-combaseapi-cotaskmemalloc), [CoTaskMemFree](/windows/win32/api/combaseapi/nf-combaseapi-cotaskmemfree)und [cotaskmemrezuweisung](/windows/win32/api/combaseapi/nf-combaseapi-cotaskmemrealloc)

Zum Zweck der Zeichen folgen Speicherverwaltung ist `CWin32Heap` die nützlichste Klasse, da Sie mehrere unabhängige Heaps erstellen kann. Wenn Sie z. b. einen separaten Heap nur für Zeichen folgen verwenden möchten, können Sie wie folgt vorgehen:

[!code-cpp[NVC_ATLMFC_Utilities#180](../atl-mfc-shared/codesnippet/cpp/implementation-of-a-custom-string-manager-basic-method_1.cpp)]

Um diesen privaten Zeichen folgen-Manager zum Verwalten des Arbeits `CString` Speichers für eine Variable zu verwenden, übergeben Sie einen Zeiger an den `CString` Manager als Parameter an den Konstruktor der Variablen:

[!code-cpp[NVC_ATLMFC_Utilities#181](../atl-mfc-shared/codesnippet/cpp/implementation-of-a-custom-string-manager-basic-method_2.cpp)]

## <a name="see-also"></a>Siehe auch

[Speicherverwaltung mit CStringT](../atl-mfc-shared/memory-management-with-cstringt.md)

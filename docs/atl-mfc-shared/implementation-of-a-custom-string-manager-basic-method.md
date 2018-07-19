---
title: Implementierung eines benutzerdefinierten Zeichenfolgenmanagers (grundlegende Methode) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- IAtlStringMgr class, using
ms.assetid: eac5d13e-cbb4-4e82-b01e-f5f2dbcb962a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c393489b8b4d0353ae37a21132f66e0618b3b794
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/06/2018
ms.locfileid: "37884583"
---
# <a name="implementation-of-a-custom-string-manager-basic-method"></a>Implementierung eines benutzerdefinierten Zeichenfolgenmanagers (grundlegende Methode)
Die einfachste Möglichkeit zum Anpassen von die Speicherbelegungsschema für Zeichenfolgendaten ist die Verwendung der ATL bereitgestellten `CAtlStringMgr` -Klasse, doch bieten Sie Ihren eigenen Arbeitsspeicher speicherbelegungsroutinen. Der Konstruktor für `CAtlStringMgr` verwendet einen einzigen Parameter: einen Zeiger auf ein `IAtlMemMgr` Objekt. `IAtlMemMgr` ist eine abstrakte Basisklasse, die eine generische Schnittstelle zu einem Heap bereitstellt. Mithilfe der `IAtlMemMgr` -Schnittstelle, die `CAtlStringMgr` ordnet zuordnet, und gibt den Arbeitsspeicher frei, die zum Speichern von Zeichenfolgendaten verwendet. Sie können entweder zuerst die `IAtlMemMgr` -Schnittstelle selbst, oder verwenden Sie eine der Klassen, fünf ATL bereitgestellten Speicher-Manager. Die bereitgestellte ATL-Speicher-Manager umschließen einfach vorhandenen Memory Allocation Möglichkeiten:  
  
-   [CCRTHeap](../atl/reference/ccrtheap-class.md) dient als Wrapper für die CRT-Heap-Standardfunktionen ([Malloc](../c-runtime-library/reference/malloc.md), [kostenlose](../c-runtime-library/reference/free.md), und [Realloc](../c-runtime-library/reference/realloc.md))  
  
-   [CWin32Heap](../atl/reference/cwin32heap-class.md) umschließt, die mit ein Win32-Heap zu behandeln, [HeapAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366597), [HeapFree](http://msdn.microsoft.com/library/windows/desktop/aa366701), und [HeapRealloc](http://msdn.microsoft.com/library/windows/desktop/aa366704)  
  
-   [Clocalheap –](../atl/reference/clocalheap-class.md) dient als Wrapper für die Win32-APIs: [LocalAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366723), [LocalFree](http://msdn.microsoft.com/library/windows/desktop/aa366730), und [LocalRealloc](http://msdn.microsoft.com/library/windows/desktop/aa366742)  
  
-   [CGlobalHeap](../atl/reference/cglobalheap-class.md) dient als Wrapper für die Win32-APIs: [GlobalAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366574), [GlobalFree](http://msdn.microsoft.com/library/windows/desktop/aa366579), und [GlobalRealloc](http://msdn.microsoft.com/library/windows/desktop/aa366590).  
  
-   [CComHeap](../atl/reference/ccomheap-class.md) dient als Wrapper für die COM-Aufgabe Allocator-APIs: [CoTaskMemAlloc](http://msdn.microsoft.com/library/windows/desktop/ms692727), [CoTaskMemFree](http://msdn.microsoft.com/library/windows/desktop/ms680722), und [CoTaskMemRealloc](http://msdn.microsoft.com/library/windows/desktop/ms687280)  
  
 Für die Verwaltung die nützlichste-Klasse ist `CWin32Heap` , da es Ihnen ermöglicht, mehrere unabhängige Heaps zu erstellen. Sie auf einen separaten Heap nur für Zeichenfolgen verwenden möchten, könnten Sie z. B. Folgendes tun:  
  
 [!code-cpp[NVC_ATLMFC_Utilities#180](../atl-mfc-shared/codesnippet/cpp/implementation-of-a-custom-string-manager-basic-method_1.cpp)]  
  
 Um diese private Zeichenfolgen-Manager verwenden, um die Verwaltung des Speichers für einen `CString` Variable, übergeben Sie einen Zeiger an den Manager als Parameter an die `CString` der Variablen-Konstruktor:  
  
 [!code-cpp[NVC_ATLMFC_Utilities#181](../atl-mfc-shared/codesnippet/cpp/implementation-of-a-custom-string-manager-basic-method_2.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [Speicherverwaltung mit CStringT](../atl-mfc-shared/memory-management-with-cstringt.md)


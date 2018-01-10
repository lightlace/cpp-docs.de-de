---
title: Implementierung eines benutzerdefinierten Zeichenfolge-Managers (grundlegende Methode) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: C++
helpviewer_keywords: IAtlStringMgr class, using
ms.assetid: eac5d13e-cbb4-4e82-b01e-f5f2dbcb962a
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b80af4fc8b463b6987f586c426bd465520f75ba6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="implementation-of-a-custom-string-manager-basic-method"></a>Implementierung eines benutzerdefinierten Zeichenfolge-Managers (grundlegende Methode)
Die einfachste Möglichkeit, die Speicherbelegungsschema anpassen für Zeichenfolgendaten ist die Verwendung der ATL bereitgestellten **CAtlStringMgr** Klasse, aber geben Sie Ihren eigenen Arbeitsspeicher Reservierungsroutinen. Der Konstruktor für **CAtlStringMgr** einen einzelnen Parameter akzeptiert: einen Zeiger auf ein `IAtlMemMgr` Objekt. `IAtlMemMgr`ist eine abstrakte Basisklasse, die eine generische Schnittstelle zu einem Heap bereitstellt. Mithilfe der `IAtlMemMgr` -Schnittstelle, die **CAtlStringMgr** zuordnet, zuordnet, und gibt den Arbeitsspeicher frei zum Speichern von Zeichenfolgendaten verwendet. Sie können entweder implementieren die `IAtlMemMgr` -Schnittstelle selbst, oder verwenden Sie eines der fünf ATL bereitgestellten Speicher-Manager-Klassen. Die bereitgestellte ATL-Speicher-Manager umschließen einfach vorhandene Arbeitsspeicher Allocation-Funktionen:  
  
-   [CCRTHeap](../atl/reference/ccrtheap-class.md) dient als Wrapper für die standard-CRT-Heapfunktionen (["malloc"](../c-runtime-library/reference/malloc.md), [freien](../c-runtime-library/reference/free.md), und [Realloc](../c-runtime-library/reference/realloc.md))  
  
-   [CWin32Heap](../atl/reference/cwin32heap-class.md) umschließt, behandeln Sie ein Win32-Heap, mit [HeapAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366597), [HeapFree](http://msdn.microsoft.com/library/windows/desktop/aa366701), und [HeapRealloc](http://msdn.microsoft.com/library/windows/desktop/aa366704)  
  
-   [Clocalheap –](../atl/reference/clocalheap-class.md) dient als Wrapper für die Win32-APIs: [LocalAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366723), [LocalAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366730), und [LocalRealloc](http://msdn.microsoft.com/library/windows/desktop/aa366742)  
  
-   [CGlobalHeap](../atl/reference/cglobalheap-class.md) dient als Wrapper für die Win32-APIs: [GlobalAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366574), [GlobalFree](http://msdn.microsoft.com/library/windows/desktop/aa366579), und [GlobalRealloc](http://msdn.microsoft.com/library/windows/desktop/aa366590).  
  
-   [CComHeap](../atl/reference/ccomheap-class.md) dient als Wrapper für die COM-Aufgabe Allocator-APIs: [CoTaskMemAlloc](http://msdn.microsoft.com/library/windows/desktop/ms692727), [CoTaskMemFree](http://msdn.microsoft.com/library/windows/desktop/ms680722), und [CoTaskMemRealloc](http://msdn.microsoft.com/library/windows/desktop/ms687280)  
  
 Für die Verwaltung des Arbeitsspeichers Zeichenfolge, die nützlichste Klasse ist `CWin32Heap` , da es Ihnen ermöglicht, mehrere unabhängige Heaps zu erstellen. Sie möchten einen separaten Heap nur für Zeichenfolgen zu verwenden, könnten Sie z. B. Folgendes tun:  
  
 [!code-cpp[NVC_ATLMFC_Utilities#180](../atl-mfc-shared/codesnippet/cpp/implementation-of-a-custom-string-manager-basic-method_1.cpp)]  
  
 Auf diese private Zeichenfolgen-Manager verwenden, um die Verwaltung des Speichers für eine `CString` Variable, übergeben Sie einen Zeiger auf den Manager als Parameter an die `CString` Variablen Konstruktor:  
  
 [!code-cpp[NVC_ATLMFC_Utilities#181](../atl-mfc-shared/codesnippet/cpp/implementation-of-a-custom-string-manager-basic-method_2.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [Speicherverwaltung mit CStringT](../atl-mfc-shared/memory-management-with-cstringt.md)


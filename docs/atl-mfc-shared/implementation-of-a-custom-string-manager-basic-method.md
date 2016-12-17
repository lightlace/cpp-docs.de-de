---
title: "Implementation of a Custom String Manager (Basic Method)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IAtlStringMgr class, Verwenden"
ms.assetid: eac5d13e-cbb4-4e82-b01e-f5f2dbcb962a
caps.latest.revision: 12
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# Implementation of a Custom String Manager (Basic Method)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die einfachste Möglichkeit, das Speicherbelegungsschema für Zeichenfolgendaten anzupassen, ist die Verwendung der ATL\-zurVerfügung kann **CAtlStringMgr**\-Klasse stellt aber eigene Speicherbelegungsroutinen.  Der Konstruktor für **CAtlStringMgr** verwendet einen einzelnen Parameter: ein Zeiger auf einen `IAtlMemMgr`\-Objekt.  `IAtlMemMgr` ist eine abstrakte Basisklasse, die eine generische Schnittstelle für einen Heap bereitstellt.  Verwenden der `IAtlMemMgr`\-Schnittstelle ordnet **CAtlStringMgr** zu, teilt neu zu und gibt den Speicher frei, der verwendet wird, um Zeichenfolgendaten zu speichern.  Sie können entweder die `IAtlMemMgr`\-Schnittstelle selbst implementieren, oder verwenden Sie eines der fünf ATL\-zurVerfügung kann Speicher\-Manager\-Klassen.  ATL\-stellte Speicherbelegungen des Umbruchs der Speicher\-Manager einfach vorhandene bereit:  
  
-   [CCRTHeap](../atl/reference/ccrtheap-class.md) Umschließt die Heapfunktionen des standardmäßigen CRT ein \([malloc](../c-runtime-library/reference/malloc.md), [frei](../c-runtime-library/reference/free.md) und [realloc](../c-runtime-library/reference/realloc.md)\)  
  
-   [CWin32Heap](../atl/reference/cwin32heap-class.md) Umschließt ein Win32\-Heaphandle, mit [HeapAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366597), [HeapFree](http://msdn.microsoft.com/library/windows/desktop/aa366701) und [HeapRealloc](http://msdn.microsoft.com/library/windows/desktop/aa366704) ein  
  
-   [CLocalHeap](../atl/reference/clocalheap-class.md) Umschließt die Win32\-API ein: [LocalAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366723), [LocalFree](http://msdn.microsoft.com/library/windows/desktop/aa366730) und [LocalRealloc](http://msdn.microsoft.com/library/windows/desktop/aa366742)  
  
-   [CGlobalHeap](../atl/reference/cglobalheap-class.md) Umschließt die Win32\-API ein: [GlobalAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366574), [GlobalFree](http://msdn.microsoft.com/library/windows/desktop/aa366579) und [GlobalRealloc](http://msdn.microsoft.com/library/windows/desktop/aa366590).  
  
-   [CComHeap](../atl/reference/ccomheap-class.md) Umschließt die COM\-Aufgaben\-Belegungsfunktion API ein: [CoTaskMemAlloc](http://msdn.microsoft.com/library/windows/desktop/ms692727), [CoTaskMemFree](http://msdn.microsoft.com/library/windows/desktop/ms680722) und [CoTaskMemRealloc](http://msdn.microsoft.com/library/windows/desktop/ms687280)  
  
 Für Zeichenfolgenspeicherverwaltung ist die zweckmäßigste Klasse `CWin32Heap`, da sie Ihnen ermöglicht, mehrere unabhängige Heaps zu erstellen.  Wenn Sie beispielsweise einen separaten Heap nur für Zeichenfolgen verwenden möchten, können Sie wie folgt vorgehen:  
  
 [!CODE [NVC_ATLMFC_Utilities#180](../CodeSnippet/VS_Snippets_Cpp/NVC_ATLMFC_Utilities#180)]  
  
 Um diesen privaten Zeichenfolgenmanager mit Speicher für eine `CString`\-Variable zu verwalten, führen Sie einen Zeiger auf den Manager als Parameter an den Konstruktor der `CString`\-Variable:  
  
 [!CODE [NVC_ATLMFC_Utilities#181](../CodeSnippet/VS_Snippets_Cpp/NVC_ATLMFC_Utilities#181)]  
  
## Siehe auch  
 [Memory Management with CStringT](../atl-mfc-shared/memory-management-with-cstringt.md)
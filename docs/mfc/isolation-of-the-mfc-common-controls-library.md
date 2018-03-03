---
title: "Isolierung der MFC-gängigsten steuert Bibliothek | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- MFC, Common Controls library
ms.assetid: 7471e6f0-49b0-47f7-86e7-8d6bc3541694
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 04ed1be46d4c3d7f36bfa501bfc933fbba41e8d1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="isolation-of-the-mfc-common-controls-library"></a>Isolierung der MFC-Bibliothek für Standardsteuerelemente
Common Controls-Bibliothek ist jetzt in MFC, ermöglichen andere Modulen (z. B. Benutzer DLLs) isolierte verschiedene Versionen der Common Controls-Bibliothek durch Angeben der Version in ihren Manifesten verwenden.  
  
 Eine MFC-Anwendung (oder Benutzercode von MFC aufgerufen) nimmt Aufrufe an APIs über Wrapperfunktionen mit dem Namen Common Controls-Bibliothek `Afx` *Funktionsname*, wobei *Funktionsname* ist der Name des eine gemeinsame API-Steuerelemente. Diese Wrapperfunktionen werden in afxcomctl32.h und afxcomctl32.inl definiert.  
  
 Sie können die [AFX_COMCTL32_IF_EXISTS](reference/run-time-object-model-services.md#afx_comctl32_if_exists) und [AFX_COMCTL32_IF_EXISTS2](reference/run-time-object-model-services.md#afx_comctl32_if_exists2) -Makros (definiert in afxcomctl32.h), um zu bestimmen, ob die Common Controls-Bibliothek eine bestimmte API statt implementiert [GetProcAddress](../build/getprocaddress.md).  
  
 Technisch gesehen Sie Aufrufe an allgemeine Steuerelemente-Bibliothek-APIs über eine Wrapperklasse `CComCtlWrapper` (definiert in afxcomctl32.h). `CComCtlWrapper`ist auch für das Laden und Entladen von comctl32.dll verantwortlich. MFC-Modulstatus enthält einen Zeiger auf eine Instanz von `CComCtlWrapper`. Sie erreichen den Wrapper Klasse mithilfe der `afxComCtlWrapper` Makro.  
  
 Beachten Sie, dass der Aufruf Common Controls-API direkt (nicht mit der MFC-Wrapperfunktionen) aus einer MFC Anwendung oder DLL funktioniert in den meisten Fällen, da die MFC-Anwendung oder den Benutzer DLL an Common Controls-Bibliothek gebunden ist es in seinem Manifest angefordert). Allerdings muss der MFC-Code selbst die Wrapper verwenden, da MFC-Code aus Benutzer-DLLs mit verschiedenen Versionen der Common Controls-Bibliothek aufgerufen werden kann.


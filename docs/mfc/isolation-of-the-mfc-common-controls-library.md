---
title: Isolierung der MFC-gängigsten steuert Bibliothek | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC, Common Controls library
ms.assetid: 7471e6f0-49b0-47f7-86e7-8d6bc3541694
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 193a0ea527cda3819a585f5b7149c823a7eb8ef7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33346814"
---
# <a name="isolation-of-the-mfc-common-controls-library"></a>Isolierung der MFC-Bibliothek für Standardsteuerelemente
Common Controls-Bibliothek ist jetzt in MFC, ermöglichen andere Modulen (z. B. Benutzer DLLs) isolierte verschiedene Versionen der Common Controls-Bibliothek durch Angeben der Version in ihren Manifesten verwenden.  
  
 Eine MFC-Anwendung (oder Benutzercode von MFC aufgerufen) nimmt Aufrufe an APIs über Wrapperfunktionen mit dem Namen Common Controls-Bibliothek `Afx` *Funktionsname*, wobei *Funktionsname* ist der Name des eine gemeinsame API-Steuerelemente. Diese Wrapperfunktionen werden in afxcomctl32.h und afxcomctl32.inl definiert.  
  
 Sie können die [AFX_COMCTL32_IF_EXISTS](reference/run-time-object-model-services.md#afx_comctl32_if_exists) und [AFX_COMCTL32_IF_EXISTS2](reference/run-time-object-model-services.md#afx_comctl32_if_exists2) -Makros (definiert in afxcomctl32.h), um zu bestimmen, ob die Common Controls-Bibliothek eine bestimmte API statt implementiert [GetProcAddress](../build/getprocaddress.md).  
  
 Technisch gesehen Sie Aufrufe an allgemeine Steuerelemente-Bibliothek-APIs über eine Wrapperklasse `CComCtlWrapper` (definiert in afxcomctl32.h). `CComCtlWrapper` ist auch für das Laden und Entladen von comctl32.dll verantwortlich. MFC-Modulstatus enthält einen Zeiger auf eine Instanz von `CComCtlWrapper`. Sie erreichen den Wrapper Klasse mithilfe der `afxComCtlWrapper` Makro.  
  
 Beachten Sie, dass der Aufruf Common Controls-API direkt (nicht mit der MFC-Wrapperfunktionen) aus einer MFC Anwendung oder DLL funktioniert in den meisten Fällen, da die MFC-Anwendung oder den Benutzer DLL an Common Controls-Bibliothek gebunden ist es in seinem Manifest angefordert). Allerdings muss der MFC-Code selbst die Wrapper verwenden, da MFC-Code aus Benutzer-DLLs mit verschiedenen Versionen der Common Controls-Bibliothek aufgerufen werden kann.


---
title: Steuert, Isolierung von der allgemeinen MFC-Bibliothek | Microsoft-Dokumentation
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
ms.openlocfilehash: 3189b2e3db594801fe417ca43867da7db2e18fd7
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46423779"
---
# <a name="isolation-of-the-mfc-common-controls-library"></a>Isolierung der MFC-Bibliothek für Standardsteuerelemente

Die allgemeine Steuerelemente-Bibliothek wird jetzt in MFC, ermöglichen andere Modulen (z.B. Benutzer DLLs) isoliert, um verschiedene Versionen der Bibliothek für allgemeine Standardsteuerelemente durch Angabe der Version in ihren Manifesten verwenden.

Eine MFC-Anwendung (oder Benutzercode, der von MFC aufgerufen) aufruft, allgemeine Steuerelemente-Bibliothek, die APIs über Wrapper-Funktionen, mit dem Namen `Afx` *FunctionName*, wobei *FunctionName* ist der Name der eine allgemeine API-Steuerelemente. Diese Wrapperfunktionen werden in afxcomctl32.h und afxcomctl32.inl definiert.

Sie können die [AFX_COMCTL32_IF_EXISTS](reference/run-time-object-model-services.md#afx_comctl32_if_exists) und [AFX_COMCTL32_IF_EXISTS2](reference/run-time-object-model-services.md#afx_comctl32_if_exists2) Makros (definiert in afxcomctl32.h), um festzustellen, ob die allgemeine Steuerelemente-Bibliothek eine bestimmte API statt implementiert [GetProcAddress](../build/getprocaddress.md).

Technisch gesehen ist es Aufrufe allgemeinen Steuerelemente-Bibliothek-APIs über eine Wrapperklasse `CComCtlWrapper` (in afxcomctl32.h definiert). `CComCtlWrapper` ist auch zuständig für das Laden und Entladen von "Comctl32.dll". MFC-Modulstatus enthält einen Zeiger auf eine Instanz von `CComCtlWrapper`. Sie erreichen, dass die Wrapper-Klasse mit dem `afxComCtlWrapper` Makro.

Beachten Sie, dass der Aufruf direkt allgemeine Steuerelemente-API (nicht die MFC-Wrapperfunktionen verwenden) aus einer MFC-Anwendung oder Benutzer-DLL funktioniert in den meisten Fällen, da die MFC-Anwendung oder Benutzer-DLL in seinem Manifest Anforderung in die allgemeine Steuerelemente-Bibliothek gebunden ist). Allerdings muss der MFC-Code selbst verwenden Sie die Wrapper, da MFC-Code aus Benutzer-DLLs mit verschiedenen Versionen der allgemeine Steuerelemente-Bibliothek aufgerufen werden kann.


---
title: 'MFC-fremde DLLs: Übersicht | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- non-MFC DLLs [C++]
- DLLs [C++], non-MFC
ms.assetid: 1ed5d1ee-e20c-47d7-801d-87ea26a73842
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 30a6fef31dee39cc6337b9b8b7dd3b66ee3adb67
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45702584"
---
# <a name="non-mfc-dlls-overview"></a>MFC-fremde DLLs: Übersicht

Eine MFC - fremde DLL ist eine DLL, die keine MFC intern verwendet, und die exportierten Funktionen in der DLL können von entweder MFC oder MFC-fremde ausführbare Dateien aufgerufen werden. Funktionen werden in der Regel aus einer MFC - fremde DLL über die standard-C-Schnittstelle exportiert.

Weitere Informationen über MFC - fremde DLLs finden Sie unter [Dynamic Link Libraries](https://msdn.microsoft.com/library/windows/desktop/ms682589) im Windows SDK.

## <a name="what-do-you-want-to-do"></a>Wie möchten Sie vorgehen?

- [Exemplarische Vorgehensweise: Erstellen und Verwenden einer Dynamic Link Library](../build/walkthrough-creating-and-using-a-dynamic-link-library-cpp.md)

- [Exportieren aus einer DLL](../build/exporting-from-a-dll.md)

- [Link an executable to a DLL (Eine ausführbare Datei mit einer DLL verknüpfen)](../build/linking-an-executable-to-a-dll.md)

- [Initialisieren einer DLL](../build/run-time-library-behavior.md#initializing-a-dll)

## <a name="what-do-you-want-to-know-more-about"></a>Worüber möchten Sie mehr erfahren?

- [Reguläre, statisch mit MFC verknüpfte MFC-DLLs](../build/regular-dlls-statically-linked-to-mfc.md)

- [Reguläre, dynamisch mit MFC verknüpfte MFC-DLLs](../build/regular-dlls-dynamically-linked-to-mfc.md)

- [MFC extension DLLs: Overview (MFC-Erweiterungs-DLLs: Übersicht)](../build/extension-dlls-overview.md)

## <a name="see-also"></a>Siehe auch

[Arten von DLLs](../build/kinds-of-dlls.md)
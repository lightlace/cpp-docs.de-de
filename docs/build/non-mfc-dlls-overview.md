---
title: 'MFC-fremde DLLs: Übersicht'
ms.date: 11/04/2016
helpviewer_keywords:
- non-MFC DLLs [C++]
- DLLs [C++], non-MFC
ms.assetid: 1ed5d1ee-e20c-47d7-801d-87ea26a73842
ms.openlocfilehash: 15cceb80b0f771c0c304572e2263b1479d6b0db7
ms.sourcegitcommit: b032daf81cb5fdb1f5a988277ee30201441c4945
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2018
ms.locfileid: "51693021"
---
# <a name="non-mfc-dlls-overview"></a>MFC-fremde DLLs: Übersicht

Eine MFC - fremde DLL ist eine DLL, die keine MFC intern verwendet, und die exportierten Funktionen in der DLL können von entweder MFC oder MFC-fremde ausführbare Dateien aufgerufen werden. Funktionen werden in der Regel aus einer MFC - fremde DLL über die standard-C-Schnittstelle exportiert.

Weitere Informationen über MFC - fremde DLLs finden Sie unter [Dynamic Link Libraries](/windows/desktop/dlls/dynamic-link-libraries) im Windows SDK.

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
---
title: Automatisierung in einer DLL
ms.date: 11/04/2016
helpviewer_keywords:
- DLLs [C++], Automation
- Automation [C++], DLLs
ms.assetid: 2728ecd1-14e2-4ae0-a946-e749e11dbb74
ms.openlocfilehash: 3cc5ca456842707a2c3de7b2fd74abc73d9a5307
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57422285"
---
# <a name="automation-in-a-dll"></a>Automatisierung in einer DLL

Wenn Sie die Automatisierungsoption im MFC-DLL-Assistenten auswählen, erhalten Sie vom Assistenten Folgendes:

- Ein Starter-Objektbeschreibungssprache (. ODL)-Datei

- Eine Include-Direktive in der Datei "stdafx.h" Afxole.h

- Eine Implementierung der `DllGetClassObject` -Funktion, die Aufrufe der **AfxDllGetClassObject** Funktion

- Eine Implementierung der `DllCanUnloadNow` -Funktion, die Aufrufe der **AfxDllCanUnloadNow** Funktion

- Eine Implementierung der `DllRegisterServer` -Funktion, die Aufrufe der [COleObjectFactory:: UpdateRegistryAll](../mfc/reference/coleobjectfactory-class.md#updateregistryall) Funktion

## <a name="what-do-you-want-to-know-more-about"></a>Worüber möchten Sie mehr erfahren?

- [Automatisierungsserver](../mfc/automation-servers.md)

## <a name="see-also"></a>Siehe auch

[DLLs in Visual C++](../build/dlls-in-visual-cpp.md)

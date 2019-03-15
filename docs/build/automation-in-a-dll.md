---
title: Automatisierung in einer DLL
ms.date: 11/04/2016
helpviewer_keywords:
- DLLs [C++], Automation
- Automation [C++], DLLs
ms.assetid: 2728ecd1-14e2-4ae0-a946-e749e11dbb74
ms.openlocfilehash: 4ac60c44348ea21f490cb312285ae88ac682cf7d
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2019
ms.locfileid: "57821247"
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

[DLLs in Visual C++](dlls-in-visual-cpp.md)

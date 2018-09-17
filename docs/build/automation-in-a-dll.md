---
title: Automatisierung in einer DLL | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- DLLs [C++], Automation
- Automation [C++], DLLs
ms.assetid: 2728ecd1-14e2-4ae0-a946-e749e11dbb74
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cde5d0e400f1bdd3f5a851d47da581380273b04a
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45717777"
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
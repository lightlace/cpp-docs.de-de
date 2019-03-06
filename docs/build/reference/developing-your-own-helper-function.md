---
title: Entwickeln eigener Hilfsfunktionen
ms.date: 11/04/2016
helpviewer_keywords:
- helper functions
ms.assetid: a845429d-68b1-4e14-aa88-f3f5343bd490
ms.openlocfilehash: 2601aff6b53e9ad3a970dbe1be008efdd7008ef8
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57424430"
---
# <a name="developing-your-own-helper-function"></a>Entwickeln eigener Hilfsfunktionen

Sie sollten eigene Version der Routine, die bestimmte Verarbeitung basierend auf den Namen der DLL oder Imports bereitgestellt. Es gibt zwei Methoden, dies zu tun: eigene Codierung, meist basierend auf den angegebenen Code ein, oder ein Hook für die angegebene Version, die mithilfe der zuvor genannten Benachrichtigungshooks.

## <a name="code-your-own"></a>Ihren eigenen Code

Dies ist recht einfach, da Sie den bereitgestellten Code im Wesentlichen als Richtlinie für den neuen Knoten verwenden können. Natürlich entsprechen den Aufrufkonventionen, und wenn auf die vom Linker generierte-Thunks zurückgegeben wird, muss es einen geeigneten Funktionszeiger zurückgeben. Einmal in Ihrem Code möglich, was ziemlich viel Sie möchten, um den Aufruf erfüllen, oder nutzen Sie den Aufruf.

## <a name="use-the-start-processing-notification-hook"></a>Verwenden Sie die Verarbeitungsbeginn

Sie werden wahrscheinlich am einfachsten, einfach einen neuen Zeiger auf eine benutzerdefinierte Benachrichtigung Hookfunktion bereitstellen, die die gleichen Werte wie die Standard-Hilfsprogramm über die DliStartProcessing empfängt. An diesem Punkt kann die Hookfunktion im Wesentlichen der neuen-Hilfsfunktion werden, da es sich bei eine erfolgreiche Rückgabe an den Standard-Helfer umgehen kann, die weitere Verarbeitung in die Standard-Hilfsprogramm.

## <a name="see-also"></a>Siehe auch

[Linkerunterstützung für verzögertes Laden von DLLs](../../build/reference/linker-support-for-delay-loaded-dlls.md)

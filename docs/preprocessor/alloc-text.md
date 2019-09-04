---
title: alloc_text-Pragma
ms.date: 08/29/2019
f1_keywords:
- vc-pragma.alloc_text
- alloc_text_CPP
helpviewer_keywords:
- alloc_text pragma
- pragmas, alloc_text
ms.assetid: 1fd7be18-e4f7-4f70-b079-6326f72b871a
ms.openlocfilehash: 7ddb12b39e068dea42f7a47f7fd937424be43725
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2019
ms.locfileid: "70216339"
---
# <a name="alloc_text-pragma"></a>alloc_text-Pragma

Namen des Codeabschnitts, in dem sich die angegebenen Funktionsdefinitionen befinden müssen. Das Pragma muss zwischen einem Funktionsdeklarator und der Funktionsdefinition für die benannten Funktionen auftreten.

## <a name="syntax"></a>Syntax

> **#pragma alloc_text (** "*Textsection*" **,** *Funktion1* [ **,** *Funktion2* ...] **)**

## <a name="remarks"></a>Hinweise

Das **alloc_text** -Pragma verarbeitet C++ keine Element Funktionen oder überladenen Funktionen. Dies gilt nur für Funktionen, die mit C-Verknüpfung deklariert sind, d. –. Funktionen, die mit der **externen "c"** -Verknüpfungs Spezifikation deklariert werden. Wenn Sie versuchen, diese Pragma für eine Funktion mit C++-Bindung zu verwenden, wird ein Compilerfehler generiert.

Da die Verwendung von `__based` mit der Verwendung von nicht unterstützt wird, muss das **alloc_text** -Pragma verwendet werden, um Abschnitts Speicherorte anzugeben. Der von *Text section* angegebene Name muss in doppelte Anführungszeichen eingeschlossen werden.

Das **alloc_text** -Pragma muss nach den Deklarationen der angegebenen Funktionen und vor den Definitionen dieser Funktionen angezeigt werden.

Funktionen, auf die in einem **alloc_text** -Pragma verwiesen wird, müssen im selben Modul wie das Pragma definiert werden. Andernfalls kann der Fehler abgefangen werden, wenn eine nicht definierte Funktion später in einen anderen Textabschnitt kompiliert wird. Obwohl das Programm in der Regel ordnungsgemäß ausgeführt wird, ist die Funktion nicht in den vorgesehenen Abschnitten zugeordnet.

Weitere Einschränkungen für **alloc_text** lauten wie folgt:

- Sie kann nicht innerhalb einer Funktion verwendet werden.

- Es muss verwendet werden, nachdem die Funktion deklariert wurde, aber bevor die Funktion definiert wurde.

## <a name="see-also"></a>Siehe auch

[Pragma-Direktiven und das __Pragma-Schlüsselwort](../preprocessor/pragma-directives-and-the-pragma-keyword.md)

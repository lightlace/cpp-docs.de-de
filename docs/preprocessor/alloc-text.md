---
title: alloc_text
ms.date: 11/04/2016
f1_keywords:
- vc-pragma.alloc_text
- alloc_text_CPP
helpviewer_keywords:
- alloc_text pragma
- pragmas, alloc_text
ms.assetid: 1fd7be18-e4f7-4f70-b079-6326f72b871a
ms.openlocfilehash: 399e8956a511f289b480e66db7f03cac0a6c7c20
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62389358"
---
# <a name="alloctext"></a>alloc_text
Namen des Codeabschnitts, in dem sich die angegebenen Funktionsdefinitionen befinden müssen. Das Pragma muss zwischen einem Funktionsdeklarator und der Funktionsdefinition für die benannten Funktionen auftreten.

## <a name="syntax"></a>Syntax

```
#pragma alloc_text( "
textsection
", function1, ... )
```

## <a name="remarks"></a>Hinweise

Die **Alloc_text** Pragma verarbeitet keine C++ Memberfunktionen oder überladene Funktionen. Dies gilt nur für Funktionen mit C-Verknüpfung deklariert – d. h. Funktionen deklariert, mit der **Extern "C"** Verknüpfungsspezifikation. Wenn Sie versuchen, diese Pragma für eine Funktion mit C++-Bindung zu verwenden, wird ein Compilerfehler generiert.

Seitdem Funktion Adressierung `__based` wird nicht unterstützt, Angabe von abschnittsspeicherorten erfordert die Verwendung der **Alloc_text** Pragma. Den Namen trägt *Textsection* muss in doppelte Anführungszeichen eingeschlossen werden.

Die **Alloc_text** Pragma muss nach den Deklarationen aller angegebenen Funktionen und vor den Definitionen dieser Funktionen angezeigt werden.

Funktionen, die auf die verwiesen wird einem **Alloc_text** Pragma sollte im selben Modul wie das Pragma definiert werden. Wenn dies nicht erfolgt ist und es wird eine nicht definierte Funktion später in einen anderen Textbereich kompiliert, ist ungewiss, ob der Fehler abgefangen wird. Obwohl das Programm in der Regel ordnungsgemäß ausgeführt wird, ist die Funktion nicht in den vorgesehenen Abschnitten zugeordnet.

Andere Einschränkungen für **Alloc_text** lauten wie folgt:

- Es kann nicht innerhalb einer Funktion verwendet werden.

- Es muss verwendet werden, nachdem die Funktion deklariert wurde, aber bevor die Funktion definiert wurde.

## <a name="see-also"></a>Siehe auch

[Pragma-Direktiven und das __Pragma-Schlüsselwort](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
---
title: "/Zc:sizedDealloc (Aktivieren der Funktionen globale Größe Aufhebung der Zuordnung) | Microsoft Docs"
ms.custom: 
ms.date: 03/06/2018
ms.technology:
- cpp-tools
ms.topic: article
f1_keywords:
- sizedDealloc
- /Zc:sizedDealloc
dev_langs:
- C++
helpviewer_keywords:
- -Zc compiler options (C++)
- sizedDealloc
- Enable Global Sized Deallocation Functions
- /Zc compiler options (C++)
- Zc compiler options (C++)
ms.assetid: 3a73ace0-4d36-420a-b699-0ca6fc0dd134
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: df3ae48e0d83fc0e0bd0f0b34b5c84c78d069a22
ms.sourcegitcommit: eeb2b5ad8d3d22514a7b9bd7d756511b69ae0ccf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2018
---
# <a name="zcsizeddealloc-enable-global-sized-deallocation-functions"></a>/Zc:sizedDealloc (Aktivieren der Funktionen globale Größe Aufhebung der Zuordnung)

Die **/Zc:sizedDealloc** Compileroption teilt dem Compiler bevorzugt verwendet globale Aufrufen `operator delete` oder `operator delete[]` Funktionen, die über einen zweiten Parameter vom Typ `size_t` Wenn die Größe des Objekts verfügbar ist. Diese Funktionen können die `size_t` Parameter zum Optimieren der Leistung deallokator.

## <a name="syntax"></a>Syntax

> **/Zc:sizedDealloc**[**-**]

## <a name="remarks"></a>Hinweise

In standard C ++ 11 können Sie statische Memberfunktionen definieren `operator delete` und `operator delete[]` , die eine zweite dauern `size_t` Parameter. Diese werden in der Regel verwendet, in Kombination mit [new-Operator](../../cpp/new-operator-cpp.md) Funktionen, um eine effizientere Zuweisungen und deallokatoren für das Objekt zu implementieren. C ++ 11 wurde jedoch kein kein äquivalenter Satz von Funktionen der Aufhebung der Zuordnung im globalen Gültigkeitsbereich definiert. In C ++ 11, Aufhebung der Zuordnung von globalen Funktionen, die über einen zweiten Parameter vom Typ `size_t` Platzierung Delete-Funktionen gelten. Sie müssen explizit aufgerufen werden, indem eine "Size"-Argument übergeben.

Standard C ++ 14 ändert das Verhalten des Compilers. Beim Definieren von globalen `operator delete` und `operator delete[]` , die einen zweiten Parameter vom Typ dauern `size_t`, der Compiler bevorzugt eine dieser Funktionen aufgerufen werden, wenn Member Bereich Versionen nicht aufgerufen werden, und die Größe des Objekts zur Verfügung steht. Der Compiler übergibt die "Size"-Argument implizit aus. Die Versionen der einzelnen Argument werden aufgerufen, wenn der Compiler die Größe des Objekts Aufhebung der Zuordnung nicht ermitteln kann. Andernfalls gelten weiterhin die üblichen Regeln für die Version der aufzurufenden Funktion Aufhebung der Zuordnung auswählen. Aufrufe an die globalen Funktionen können explizit angegeben werden, durch voranstellen des Bereichsauflösungsoperators (`::`) für die Aufhebung der Zuordnung-Funktionsaufruf.

Visual C++ ab Visual Studio 2015 implementiert standardmäßig diese C ++ 14-Standardverhalten. Sie können dies explizit angeben, durch Festlegen der **/Zc:sizedDealloc** -Compileroption. Dies stellt eine potenziell wichtige Änderung. Verwenden Sie die **/Zc:sizedDealloc-** Option aus, um das alte Verhalten beibehalten, wenn Codes Platzierung Delete-Operatoren definiert, mit dem zweiten Parameter vom Typ `size_t`. Die Implementierungen für die Bibliothek von Visual Studio die Aufhebung der Zuordnung von globalen Funktionen, den zweiten Parameter vom Typ `size_t` die Versionen der einzelnen Parameter aufrufen. Wenn Ihr Code nur einzelne-Parameter globale liefert Delete-Operator und dem Operator delete [], standardmäßigen Library Implementierungen der globalen Größeninformationen Funktionen Ihrer globalen Funktionen aufrufen.

Die **/Zc:sizedDealloc** Compileroption ist standardmäßig aktiviert. Die [/ liberalen-](permissive-standards-conformance.md) Option wirkt sich nicht **/Zc:sizedDealloc**.

Weitere Informationen über Konformitätsprobleme in Visual C++ finden Sie unter [Nonstandard Behavior](../../cpp/nonstandard-behavior.md).

## <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).

1. Aus der **Konfigurationen** Dropdown-Menü, und wählen Sie **alle Konfigurationen**.

1. Wählen Sie die **Konfigurationseigenschaften** > **C/C++-** > **Befehlszeile** Eigenschaftenseite.

1. Ändern der **Zusatzoptionen** Eigenschaft einschließen **/Zc:sizedDealloc** oder **/Zc:sizedDealloc-** und wählen Sie dann **OK**.

## <a name="see-also"></a>Siehe auch

[Compileroptionen](../../build/reference/compiler-options.md)<br/>
[Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)<br/>
[/Zc (Übereinstimmung)](../../build/reference/zc-conformance.md)<br/>

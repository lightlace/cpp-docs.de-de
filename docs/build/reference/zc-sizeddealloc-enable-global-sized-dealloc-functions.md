---
title: /Zc:sizedDealloc (aktivieren Zuordnungsaufhebungsfunktionen globaler Größe)
ms.date: 03/06/2018
f1_keywords:
- sizedDealloc
- /Zc:sizedDealloc
helpviewer_keywords:
- -Zc compiler options (C++)
- sizedDealloc
- Enable Global Sized Deallocation Functions
- /Zc compiler options (C++)
- Zc compiler options (C++)
ms.assetid: 3a73ace0-4d36-420a-b699-0ca6fc0dd134
ms.openlocfilehash: dc381058c6a2ef84542be1d3cdd00c410aa51c2f
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2019
ms.locfileid: "57809300"
---
# <a name="zcsizeddealloc-enable-global-sized-deallocation-functions"></a>/Zc:sizedDealloc (aktivieren Zuordnungsaufhebungsfunktionen globaler Größe)

Die **/Zc:sizedDealloc** Compiler-Option weist den Compiler bevorzugt verwendet globale Aufrufen `operator delete` oder `operator delete[]` Funktionen, die einen zweiten Parameter des Typs aufweisen `size_t` Wenn die Größe des Objekts verfügbar ist. Diese Funktionen können Sie die `size_t` Parameter deallokator Leistung zu optimieren.

## <a name="syntax"></a>Syntax

> **/Zc:sizedDealloc**[**-**]

## <a name="remarks"></a>Hinweise

In der C ++ 11-standard, können Sie statische Memberfunktionen definieren `operator delete` und `operator delete[]` , die eine Sekunde dauern `size_t` Parameter. Diese werden in der Regel verwendet, in Kombination mit [new-Operator](../../cpp/new-operator-cpp.md) Funktionen, um eine effizientere Zuweisungen und deallokatoren für das Objekt zu implementieren. Allerdings haben C ++ 11 keinen entsprechenden Satz von Funktionen im globalen Gültigkeitsbereich definiert. In C ++ 11, globale Funktionen, die einen zweiten Parameter des Typs `size_t` Placement-Delete-Funktionen gelten. Sie müssen explizit aufgerufen werden, indem eine "Size"-Argument übergeben.

Die C ++ 14-standard ändert das Verhalten des Compilers. Beim Definieren von globalen `operator delete` und `operator delete[]` , die muss es sich um eines zweiten Parameters vom Typ `size_t`, der Compiler es vorzieht, rufen diese Funktionen auf, wenn Member Bereich Versionen nicht aufgerufen werden, und die Größe des Objekts zur Verfügung steht. Der Compiler übergibt die "Size"-Argument implizit. Die einzelnen Argument-Versionen werden immer dann aufgerufen, wenn der Compiler nicht ermitteln kann, die Größe des Objekts freigegeben wird. Andernfalls gelten die üblichen Regeln für die Wahl der Version die Aufhebung der, die aufzurufende zuordnungsaufhebungsfunktion weiterhin ein. Aufrufe an die globalen Funktionen können explizit angegeben werden, indem Sie den Bereichsauflösungsoperator voranstellen (`::`) auf den Funktionsaufruf Aufhebung der Zuordnung.

Visual C++ ab Visual Studio 2015 implementiert standardmäßig diese C ++ 14-Standardverhalten. Sie können dies explizit angeben, durch Festlegen der **/Zc:sizedDealloc** -Compileroption. Dies stellt eine potenziell wichtige Änderung. Verwenden Sie die **/Zc:sizedDealloc-** Option aus, um das alte Verhalten, z. B. beibehalten, wenn Ihr Code Placement-Delete-Operatoren definiert, die einen zweiten Parameter des Typs verwenden `size_t`. Die standardimplementierungen für die Bibliothek von Visual Studio von der globalen Funktionen, die den zweiten Parameter vom Typ `size_t` rufen Sie die Versionen der einzelnen Parameter. Wenn Ihr Code nur einzigen Parameter globale bereitstellt Delete-Operator und dem Operator delete [], die Bibliothek standardimplementierungen der Größeninformationen für globale Funktionen Ihrer globalen Funktionen aufrufen.

Die **/Zc:sizedDealloc** Compiler-Option ist standardmäßig aktiviert. Die [/ PERMISSIVE--](permissive-standards-conformance.md) Option hat keine Auswirkungen auf **/Zc:sizedDealloc**.

Weitere Informationen über Konformitätsprobleme in Visual C++ finden Sie unter [Nonstandard Behavior](../../cpp/nonstandard-behavior.md).

## <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Festlegen von C++-Compiler und die Build-Eigenschaften in Visual Studio](../working-with-project-properties.md).

1. Von der **Konfigurationen** Dropdownmenü, und wählen Sie **alle Konfigurationen**.

1. Wählen Sie die **Konfigurationseigenschaften** > **C/C++-** > **Befehlszeile** Eigenschaftenseite.

1. Ändern der **zusätzliche Optionen** Eigenschaft sollen **/Zc:sizedDealloc** oder **/Zc:sizedDealloc-** und wählen Sie dann **OK**.

## <a name="see-also"></a>Siehe auch

[MSVC-Compiler-Optionen](compiler-options.md)<br/>
[MSVC-Compiler-Befehlszeilensyntax](compiler-command-line-syntax.md)<br/>
[/Zc (Übereinstimmung)](zc-conformance.md)<br/>

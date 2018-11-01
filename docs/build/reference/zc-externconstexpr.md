---
title: '/ Zc: externconstexpr (externe Constexpr Variablen aktivieren)'
ms.date: 02/28/2018
f1_keywords:
- /Zc:externConstexpr
helpviewer_keywords:
- -Zc:externConstexpr compiler option (C++)
- extern constexpr variables (C++)
ms.assetid: 4da5e33a-2e4d-4ed2-8616-bd8f43265c27
ms.openlocfilehash: a9efa2fa191cbdda99e057ac9329d79bc598743c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50510694"
---
# <a name="zcexternconstexpr-enable-extern-constexpr-variables"></a>/ Zc: externconstexpr (externe Constexpr Variablen aktivieren)

Die **/Zc: externconstexpr** -Compileroption informiert den Compiler an, der C++-Standard entsprechen, und ermöglichen externen Verknüpfung für `constexpr` Variablen. Standardmäßig gibt Visual Studio immer eine `constexpr` Variable interne Verknüpfung, selbst wenn Sie angeben, die `extern` Schlüsselwort.

## <a name="syntax"></a>Syntax

> **/Zc:externConstexpr**[**-**]

## <a name="remarks"></a>Hinweise

Die **/Zc: externconstexpr** Compileroption veranlasst den Compiler, Variablen, die mit externen Verknüpfung zuweisen `extern constexpr`. In früheren Versionen von Visual Studio, und klicken Sie in der Standardeinstellung oder, wenn **/Zc:externConstexpr-** angegeben ist, wird Visual Studio wendet internen Verknüpfung, `constexpr` Variablen auch dann, wenn die `extern` -Schlüsselwort wird verwendet. Die **/Zc: externconstexpr** Option ist verfügbar in Visual Studio 2017 Update 15.6 ab. und ist standardmäßig deaktiviert. Die [/ PERMISSIVE--](permissive-standards-conformance.md) Option ermöglicht keine **/Zc: externconstexpr**.

Wenn eine Headerdatei eine deklarierte Variable enthält `extern constexpr`, müssen markiert werden [__declspec(selectany)](../../cpp/selectany.md) um die doppelten Deklarationen in einer einzelnen Instanz in der verknüpften Binärdatei zusammenzuführen. Andernfalls sehen Sie möglicherweise die Linker-Fehler, z. B. LNK2005 für Verstöße gegen die One Definition Rule.

### <a name="to-set-this-compiler-option-in-visual-studio"></a>So legen Sie diese Compileroption in Visual Studio fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Ausführliche Informationen finden Sie unter [Working with Project Properties (Arbeiten mit Projekteigenschaften)](../../ide/working-with-project-properties.md).

1. Wählen Sie die **Konfigurationseigenschaften** > **C/C++-** > **Befehlszeile** Eigenschaftenseite.

1. Hinzufügen **/Zc: externconstexpr** oder **/Zc:externConstexpr-** auf die **zusätzliche Optionen:** Bereich.

## <a name="see-also"></a>Siehe auch

[/Zc (Übereinstimmung)](../../build/reference/zc-conformance.md)<br/>
[Auto-Schlüsselwort](../../cpp/auto-keyword.md)
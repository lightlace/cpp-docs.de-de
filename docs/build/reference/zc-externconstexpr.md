---
title: /Zc:externConstexpr (aktivieren "extern" Constexpr-Variablen) | Microsoft Docs
ms.custom: 
ms.date: 9/29/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /Zc:externConstexpr
dev_langs: C++
helpviewer_keywords:
- -Zc:externConstexpr compiler option (C++)
- extern constexpr variables (C++)
ms.assetid: 4da5e33a-2e4d-4ed2-8616-bd8f43265c27
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: ff9d6a1739898e862df0f6ce0be0a941eb06c7e8
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="zcexternconstexpr-enable-extern-constexpr-variables"></a>/Zc:externConstexpr (aktivieren "extern" Constexpr-Variablen)

Die **/Zc:externConstexpr** Compileroption teilt dem Compiler mit der C++-Standard entsprechen und externen Verknüpfung für zulassen `constexpr` Variablen. Standardmäßig gibt Visual Studio immer eine `constexpr` Variable interne Verknüpfung, selbst wenn Sie angeben, die `extern` Schlüsselwort.

## <a name="syntax"></a>Syntax

> /Zc:externConstexpr [-]

## <a name="remarks"></a>Hinweise

Die **/Zc:externConstexpr** (Compileroption) veranlasst den Compiler, Variablen, die deklariert, indem externe Verknüpfung zuweisen `extern constexpr`. Die **/Zc:externConstexpr** Option ist verfügbar in Visual Studio 2017 Update 15.5 ab. In früheren Versionen von Visual Studio, und standardmäßig oder wenn **/Zc:externConstexpr-** angegeben ist, wird Visual Studio wendet interne Verknüpfung zu `constexpr` Variablen erstellen, selbst wenn die `extern` -Schlüsselwort wird verwendet.

Wenn eine Headerdatei eine deklarierte Variable enthält `extern constexpr`, müssen markiert werden [__declspec(selectany)](../../cpp/selectany.md) um doppelten Deklarationen in einer einzelnen Instanz in der verknüpften Binärdatei zusammenzuführen. Andernfalls wird möglicherweise Linkerfehler, z. B. LNK2005 für Verstöße gegen die One Definition Rule angezeigt.

### <a name="to-set-this-compiler-option-in-visual-studio"></a>So legen Sie diese Compileroption in Visual Studio fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).

1. Klicken Sie unter **Konfigurationseigenschaften**, erweitern Sie **C/C++-** und wählen Sie dann **Befehlszeile**.

1. Hinzufügen **/Zc:externConstexpr** oder **/Zc:externConstexpr-** auf die **zusätzliche Optionen:** Bereich.

## <a name="see-also"></a>Siehe auch

[/ Zc (Übereinstimmung)](../../build/reference/zc-conformance.md)  
[Auto-Schlüsselwort](../../cpp/auto-keyword.md)
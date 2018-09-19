---
title: Sonderzeichen in einem Makefile | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- NMAKE program, special characters
- makefiles, special characters
- special characters, in NMAKE macros
- macros, special characters
ms.assetid: 92c34ab5-ca6b-4fc0-bcf4-3172eaeda9f0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3ae77e769672dcc88a9dd41c901424c8c8150e6b
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45709358"
---
# <a name="special-characters-in-a-makefile"></a>Sonderzeichen in einem Makefile

Um eine NMAKE-Sonderzeichen als Literalzeichen zu verwenden, platzieren Sie ein Caretzeichen (^) vor. NMAKE: ignoriert Caretzeichen an, die vor anderen Zeichen. Die Sonderzeichen sind:

`:  ;  #  (  )  $  ^  \  {  }  !  @  —`

Ein Caretzeichen (^) in eine Zeichenfolge in Anführungszeichen wird als literal Zirkumflexzeichen behandelt. Eine Einfügemarke am Ende einer Zeile Fügt ein literales Zeilenumbruchzeichen in eine Zeichenfolge oder ein Makro.

In Makros, einen umgekehrten Schrägstrich (\\) gefolgt durch eine neue Zeile-Zeichen wird durch ein Leerzeichen ersetzt.

In Befehlen ist ein Prozentzeichen (%) den Dateibezeichner. Um dieses Zeichen in einen Befehl zu repräsentieren, geben Sie ein doppelten Prozentzeichen (%) anstelle einer einzigen Datei aus. In anderen Situationen interpretiert NMAKE ein einzelnes % praktisch, aber es immer einen Double-Wert interpretiert %% als ein einzelnes %. Aus diesem Grund zur Darstellung eines Literals %%, geben Sie entweder drei Prozentzeichen %%%, oder vier Prozentzeichen, %%%.

Um das Dollarzeichen ($) als Literalzeichen in einem Befehl zu verwenden, geben Sie zwei Dollarzeichen ($$). Diese Methode kann auch verwendet werden, in anderen Situationen, in dem ^ $ funktioniert.

## <a name="see-also"></a>Siehe auch

[Inhalt eines Makefiles](../build/contents-of-a-makefile.md)
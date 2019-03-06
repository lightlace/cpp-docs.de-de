---
title: Sonderzeichen in einem Makefile
ms.date: 11/04/2016
helpviewer_keywords:
- NMAKE program, special characters
- makefiles, special characters
- special characters, in NMAKE macros
- macros, special characters
ms.assetid: 92c34ab5-ca6b-4fc0-bcf4-3172eaeda9f0
ms.openlocfilehash: e2703adbbdba392b1a317e2656c6f3dba30a36b6
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57420754"
---
# <a name="special-characters-in-a-makefile"></a>Sonderzeichen in einem Makefile

Um eine NMAKE-Sonderzeichen als Literalzeichen zu verwenden, platzieren Sie ein Caretzeichen (^) vor. NMAKE: ignoriert Caretzeichen an, die vor anderen Zeichen. Die Sonderzeichen sind:

`:  ;  #  (  )  $  ^  \  {  }  !  @  —`

Ein Caretzeichen (^) in eine Zeichenfolge in Anführungszeichen wird als literal Zirkumflexzeichen behandelt. Eine Einfügemarke am Ende einer Zeile Fügt ein literales Zeilenumbruchzeichen in eine Zeichenfolge oder ein Makro.

In Makros, einen umgekehrten Schrägstrich (\\) gefolgt durch eine neue Zeile-Zeichen wird durch ein Leerzeichen ersetzt.

In Befehlen ein Prozentzeichen (%) Stellt den Dateibezeichner. Um dieses Zeichen in einen Befehl zu repräsentieren, geben Sie ein doppelten Prozentzeichen (%) anstelle einer einzigen Datei. In anderen Situationen interpretiert NMAKE ein einzelnes % praktisch, aber es immer einen Double-Wert interpretiert %% als ein einzelnes %. Aus diesem Grund zur Darstellung eines Literals %%, geben Sie entweder drei Prozentzeichen %%%, oder vier Prozentzeichen, %%%.

Um das Dollarzeichen ($) als Literalzeichen in einem Befehl zu verwenden, geben Sie zwei Dollarzeichen ($$). Diese Methode kann auch verwendet werden, in anderen Situationen, in dem ^ $ funktioniert.

## <a name="see-also"></a>Siehe auch

[Inhalt eines Makefiles](../build/contents-of-a-makefile.md)

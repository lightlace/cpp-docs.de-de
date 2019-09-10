---
title: Zeichentests
ms.date: 11/04/2016
ms.assetid: 376ba061-bae3-427e-9569-33fa5949a199
ms.openlocfilehash: b02d07ca2796e5088c3021f1ae8795ea92761943
ms.sourcegitcommit: 180f63704f6ddd07a4172a93b179cf0733fd952d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "70740103"
---
# <a name="character-testing"></a>Zeichentests

**ANSI 4.3.1** Die Zeichensätze, auf die die Funktionen `isalnum`, `isalpha`, `iscntrl`, `islower`, `isprint` und `isupper` prüfen

Die folgende Liste beschreibt diese Funktionen, wie sie vom Microsoft C-Compiler implementiert werden.

|Funktion|Tests für|
|--------------|---------------|
|`isalnum`|Die Zeichen 0-9, A-Z, a-z ASCII 48-57, 65-90, 97-122|
|`isalpha`|Die Zeichen A-Z, a-z ASCII 65-90, 97-122|
|`iscntrl`|ASCII 0 –31, 127|
|`islower`|Die Zeichen A–Z ASCII 97-122|
|`isprint`|Die Zeichen A-Z, a-z, 0-9, Satzzeichen, Leerzeichen-ASCII 32-126|
|`isupper`|Die Zeichen A–Z ASCII 65-90|

## <a name="see-also"></a>Siehe auch

[Bibliotheksfunktionen](../c-language/library-functions.md)

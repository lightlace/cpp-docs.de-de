---
title: Platzhaltererweiterung
ms.date: 11/04/2016
f1_keywords:
- _setargv
helpviewer_keywords:
- asterisk wildcard
- _setargv function
- command line [C++], processing arguments
- command line [C++], wildcards
- command-line wildcards
- question mark, wildcard
ms.assetid: 1a543398-607b-4404-93d1-45d290bde638
ms.openlocfilehash: 1fdea297bb45a06a08bde4f63f90eabef6ddb539
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/05/2019
ms.locfileid: "74857176"
---
# <a name="wildcard-expansion"></a>Platzhaltererweiterung

**Microsoft-spezifisch**

Sie können Platzhalter – das Fragezeichen (?) und das Sternchen (*) – verwenden, um Dateinamen- und Pfadargumente in der Befehlszeile anzugeben.

Befehlszeilenargumente werden von einer Routine mit dem Namen `_setargv` behandelt (oder in der breit Zeichen Umgebung `_wsetargv`), die standardmäßig keine Platzhalter in separate Zeichen folgen im `argv` Zeichen folgen Array erweitert. Weitere Informationen zum Aktivieren der Platzhalter Erweiterung finden Sie unter Erweitern von Platzhalter [Argumenten](../c-language/expanding-wildcard-arguments.md).

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[main: Programmstart](../cpp/main-program-startup.md)
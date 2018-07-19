---
title: Linkoptionen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- nothrownew.obj
- newmode.obj
- noenv.obj
- psetargv.obj
- loosefpmath.obj
- smallheap.obj
- fp10.obj
- nochkclr.obj
- chkstk.obj
- pcommode.obj
- pnoenv.obj
- link options [C++]
- invalidcontinue.obj
- pnothrownew.obj
- pwsetargv.obj
- pinvalidcontinue.obj
- wsetargv.obj
- binmode.obj
- setargv.obj
- noarg.obj
- pnewmode.obj
- commode.obj
- pthreadlocale.obj
- pbinmode.obj
- threadlocale.obj
- pnoarg.obj
ms.assetid: 05b5a77b-9dd1-494b-ae46-314598c770bb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 98965b94c83b69e15c38319d7bc5a6e4151b323e
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2018
ms.locfileid: "34704885"
---
# <a name="link-options"></a>Linkoptionen

Das Verzeichnis „CRT lib“ umfasst eine Anzahl von kleinen Dateien, die bestimmte CRT-Funktionen ohne Codeänderung ermöglichen. Diese werden als "Linkoptionen" bezeichnet, da Sie sie nur der Linkerbefehlszeile hinzufügen müssen, um sie zu verwenden.

Die reinen CLR-Versionen dieser Objekte sind in Visual Studio 2015 als veraltet markiert und werden in Visual Studio 2017 nicht unterstützt. Verwenden Sie die Standardversionen für nativen Code und /CLR-Code.

|Native und /CLR|Reiner Modus|description|
|----------------------|---------------|-----------------|
|binmode.obj|pbinmode.obj|Legt den Standard-Dateiübersetzungsmodus auf „binär“ fest. Siehe [_fmode](../c-runtime-library/fmode.md).|
|chkstk.obj|n/v|Bietet Stapelüberprüfung und alloca-Unterstützung, wenn CRT nicht verwendet wird.|
|commode.obj|pcommode.obj|Legt das globale Commit-Flag auf „commit“ fest. Siehe [fopen, _wfopen](../c-runtime-library/reference/fopen-wfopen.md) und [fopen_s, _wfopen_s](../c-runtime-library/reference/fopen-s-wfopen-s.md).|
|fp10.obj|n/v|Ändert das Standard-Präzisionssteuerelement in 64 Bit. Siehe [Gleitkommaunterstützung](../c-runtime-library/floating-point-support.md).|
|invalidcontinue.obj|pinvalidcontinue.obj|Legt einen standardmäßigen Handler für ungültige Parameter fest, der nichts bewirkt; d.h., dass ungültige Parameter, die an CRT-Funktionen übergeben werden, nur errno festlegen und ein Fehlerergebnis zurückgeben.|
|loosefpmath.obj|n/v|Stellt sicher, dass der Gleitkommacode nicht normale Werte toleriert.|
|newmode.obj|pnewmode.obj|Veranlasst [malloc](../c-runtime-library/reference/malloc.md), die neuen Handler als Fehler aufzurufen. Siehe [_set_new_mode](../c-runtime-library/reference/set-new-mode.md), [_set_new_handler](../c-runtime-library/reference/set-new-handler.md), [calloc](../c-runtime-library/reference/calloc.md), und [realloc](../c-runtime-library/reference/realloc.md).|
|noarg.obj|pnoarg.obj|Deaktiviert alle Verarbeitungsvorgänge von argc und argv.|
|nochkclr.obj|n/v|Ohne Wirkung. Aus Ihrem Projekt entfernen.|
|noenv.obj|pnoenv.obj|Deaktiviert die Erstellung einer zwischengespeicherten Umgebung für CRT.|
|nothrownew.obj|pnothrownew.obj|Ermöglicht die nicht auslösende Version von „neu“ in CRT. Siehe [Operatoren „new“ und „delete“](../cpp/new-and-delete-operators.md).|
|setargv.obj|psetargv.obj|Ermöglicht die Platzhaltererweiterung eines Befehlszeilenarguments. Siehe [Erweitern von Platzhalterargumenten](../c-language/expanding-wildcard-arguments.md).|
|threadlocale.obj|pthreadlocale.obj|Ermöglicht das threadspezifische Gebietsschema standardmäßig für alle neuen Threads.|
|wsetargv.obj|pwsetargv.obj|Ermöglicht die Platzhaltererweiterung eines Befehlszeilenarguments. Siehe [Erweitern von Platzhalterargumenten](../c-language/expanding-wildcard-arguments.md).|

## <a name="see-also"></a>Siehe auch

- [CRT-Bibliotheksfunktionen](../c-runtime-library/crt-library-features.md)

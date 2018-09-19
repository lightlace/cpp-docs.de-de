---
title: C-Laufzeitfehler von R6002 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- R6002
dev_langs:
- C++
helpviewer_keywords:
- R6002
ms.assetid: 8fbbe65a-9c43-459e-8342-e1f6d1cef7d0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dc23cf3c692eef37a86b5385d2e9e3a68340374e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46080921"
---
# <a name="c-runtime-error-r6002"></a>C-Laufzeitfehler von R6002

gleitkommaunterstützung nicht geladen

Die erforderlichen Gleitkomma-Bibliothek wurde nicht verknüpft.

> [!NOTE]
>  Wenn Sie diese Fehlermeldung beim Ausführen einer app auftritt, wurde die app beendet, da er ein internes Problem aufweist. Es gibt mehrere mögliche Gründe für diesen Fehler, aber dies wird häufig verursacht einen Fehler im Code der app oder beim Versuch, eine app auszuführen, die für den bestimmten Computer-Prozessor nicht erstellt wurde.
>
>  Sie können versuchen, diesen Fehler zu beheben, indem Sie folgende Schritte ausführen:
>
>  -   Verwenden der **Apps und Features** oder **Programme und Funktionen** auf der Seite die **Systemsteuerung** zu reparieren oder installieren Sie das Programm neu.
> -   Überprüfen Sie **Windows Update** in die **Systemsteuerung** für Softwareupdates.
> -   Überprüfen Sie nach einer aktualisierten Version der app. Wenn das Problem weiterhin besteht, wenden Sie sich an den app-Anbieter.

**Informationen für Programmierer**

Dieser Fehler kann in Ihrer app auftreten, wenn die Gleitkomma-Bibliothek wurde nicht verknüpft. Überprüfen Sie eine der folgenden Ursachen:

- Eine Formatzeichenfolge für einen `printf_s` oder `scanf_s` Funktion enthalten, eine Spezifikation Gleitkommaformat und das Programm keine Gleitkommazahlen-Punktwerte oder Variablen enthalten. Um dieses Problem zu beheben, verwenden eines gleitkommaarguments der Gleitkommaformat-Spezifikation entsprechen, oder führen Sie eine Gleitkommazahl Zuweisung an anderer Stelle im Programm. Dies bewirkt, dass gleitkommaunterstützung geladen werden.

- Der Compiler minimiert eines Programms Größe gleitkommaunterstützung nur bei Bedarf laden. Der Compiler kann nicht feststellen Gleitkommaoperationen oder Gleitkommaformat-Spezifikationen in Formatzeichenfolgen, sodass sie nicht die benötigten Gleitkommaroutinen geladen wird. Um dieses Problem zu beheben, verwenden Sie eine Spezifikation Gleitkommaformat und Angeben eines gleitkommaarguments oder eine Gleitkommazahl Zuweisung an anderer Stelle im Programm ausführen. Dies bewirkt, dass gleitkommaunterstützung geladen werden.

- In einem gemischten Sprachen-Programm wurde eine C-Bibliothek vor einer Bibliothek FORTRAN angegeben, wenn das Programm verknüpft wurde. Verknüpfen Sie erneut aus, und geben Sie der C-Bibliothek zuletzt.
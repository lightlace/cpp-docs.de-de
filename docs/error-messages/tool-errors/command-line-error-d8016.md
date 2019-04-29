---
title: Befehlszeilenfehler D8016
ms.date: 11/04/2016
f1_keywords:
- D8016
helpviewer_keywords:
- D8016
ms.assetid: eec51312-7471-4f92-94b2-d517cafc8ef5
ms.openlocfilehash: c1e2e3e28f8556416f58d68f8ef1df4b220bc54c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62399966"
---
# <a name="command-line-error-d8016"></a>Befehlszeilenfehler D8016

Option "1" und "option2"-Befehlszeilenoptionen sind nicht kompatibel

Die Optionen der Befehlszeilen können nicht zusammen angegeben werden.

Überprüfen Sie die Umgebungsvariablen wie CL, Optionsangaben.

**"/ CLR"** impliziert **/EHa**, und Sie können angeben, alle anderen **/EH** Compileroption mit **"/ CLR"**. Weitere Informationen finden Sie unter [/clr (Common Language Runtime-Kompilierung)](../../build/reference/clr-common-language-runtime-compilation.md).

Sie möglicherweise D8016 ein Visual C++ 6.0-Projekt wird aktualisiert: der Assistent zur Aktualisierung des Projekts aktivieren kann **/RTC** -Außerkraftsetzungen für jede Quellcodedatei in das Projekt, das die **/RTC** für das Projekt festlegen.  Ändern Sie zum Beheben der **/RTC** für jede Quellcodedatei in das Projekt festlegen, um die Standardeinstellung, was bedeutet die projekteinstellung für **/RTC** wird für jede Datei wirksam werden.

Finden Sie unter [/RTC (Run-Time Error Checks)](../../build/reference/rtc-run-time-error-checks.md) Informationen zum Ändern der **/RTC** Einstellung der Eigenschaft.
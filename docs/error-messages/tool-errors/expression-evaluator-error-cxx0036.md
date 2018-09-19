---
title: Ausdrucksauswertungsfehler CXX0036 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- CXX0036
dev_langs:
- C++
helpviewer_keywords:
- CXX0036
- CAN0036
ms.assetid: 383404be-df5b-4eec-b113-df21bb5d269d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e2d82a1254a11dbda3164ea1c350dc14e2b1a122
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46050111"
---
# <a name="expression-evaluator-error-cxx0036"></a>Ausdrucksauswertungsfehler CXX0036

Falscher Kontext {...} Angabe

Diese Meldung kann von einer von mehreren Fehlern bei der Verwendung des Operators Kontext generiert werden (**{}**).

- Die Syntax des Operators Kontext (**{}**) wurde falsch angegeben.

     Die Syntax des Operators Kontext lautet:

     {*Funktion*,*Modul*,*Dll*}*Ausdruck*

     Dies gibt den Kontext der *Ausdruck*. Der Kontextoperator hat die gleiche Rangfolge und die Verwendung als eine Typumwandlung.

     Nachfolgende Trennzeichen kann ausgelassen werden. Wenn eine der *Funktion*, *Modul*, oder *Dll* enthält ein Komma, müssen Sie den gesamten Namen in Klammern einschließen.

- Der Funktionsname falsch eingegeben wurde, oder im festgelegten Modul oder Dynamic Link Library nicht vorhanden.

     Da C Groß-/Kleinschreibung beachtet, wird *Funktion* muss genau zugewiesen werden, da es in der Quelle definiert wurde.

- Das Modul oder die DLL konnte nicht gefunden werden.

     Überprüfen Sie den vollständigen Pfadnamen des angegebenen Moduls oder der DLL.

Dieser Fehler ist mit CAN0036 identisch.
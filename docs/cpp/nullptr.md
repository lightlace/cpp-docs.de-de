---
title: "\"nullptr\" | Microsoft-Dokumentation"
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- nullptr_cpp
dev_langs:
- C++
helpviewer_keywords:
- nullptr keyword [C++]
ms.assetid: e9d80ea6-2506-4eb5-b47b-2349df085832
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 06586d7d4374ec1763e43a1eaf3235c37dc72cd1
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46077944"
---
# <a name="nullptr"></a>nullptr

Legt eine NULL-Zeiger-Konstante vom Typ `std::nullptr_t` fest, der in einen beliebigen unformatierten Zeigertyp konvertiert werden kann.  Obwohl Sie das Schlüsselwort verwenden, können **"nullptr"** ohne Header, wenn Ihr Code den Typ verwendet `std::nullptr_t`, und Sie es definieren müssen, indem Sie den Header `<cstddef>`.

> [!NOTE]
>  Die **"nullptr"** Schlüsselwort wird auch definiert, in C++ / CLI für Anwendungen mit verwaltetem Code und ist nicht mit dem ISO-Standard C++-Schlüsselwort austauschbar. Wenn Ihr Code mit kompiliert werden kann die ["/ CLR"](../build/reference/clr-common-language-runtime-compilation.md) Compileroption, die verwalteten Code ausgerichtet ist, verwenden Sie dann `__nullptr` in eine beliebige Codezeile, in denen Sie sicherstellen müssen, dass der Compiler die systemeigene C++-Interpretation verwendet. Weitere Informationen finden Sie unter ["nullptr"](../windows/nullptr-cpp-component-extensions.md).

## <a name="remarks"></a>Hinweise

Vermeiden Sie die Verwendung von NULL oder 0 (null) (`0`) als eine Konstante null-Zeiger **"nullptr"** ist weniger anfällig für missbräuchliche Verwendung und besser in den meisten Fällen funktioniert.  Beispiel: Wenn `func(std::pair<const char *, double>)` vorgegeben ist, verursacht der Aufruf von `func(std::make_pair(NULL, 3.14))` einen Compilerfehler.  Die Makro-NULL wird auf `0` erweitert, sodass der Aufruf `std::make_pair(0, 3.14)` den Wert `std::pair<int, double>` zurückgibt, der nicht in den Parametertyp `std::pair<const char *, double>` von func() konvertierbar ist.  Durch Aufrufen von `func(std::make_pair(nullptr, 3.14))` ist die Kompilierung erfolgreich, da `std::make_pair(nullptr, 3.14)` den Wert `std::pair<std::nullptr_t, double>` zurückgibt, der in `std::pair<const char *, double>` konvertiert werden kann.

## <a name="see-also"></a>Siehe auch

[Schlüsselwörter](../cpp/keywords-cpp.md)<br/>
[nullptr](../windows/nullptr-cpp-component-extensions.md)
---
title: '&lt;exception&gt; | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- <exception>
dev_langs:
- C++
helpviewer_keywords:
- exception header
ms.assetid: 28900768-5dd7-4834-b907-5e37ab3407db
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bbd57085225bb21b9f7ce8bd34c537d3bc414797
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33845816"
---
# <a name="ltexceptiongt"></a>&lt;exception&gt;

Definiert einige Typen und Funktionen, die mit der Behandlung von Ausnahmen in Beziehung stehen. Ausnahmebehandlung wird ist in Situationen verwendet, in denen das System von einem Fehler wiederhergestellt werden kann. Sie stellt eine Methode bereit, mit der die Steuerung von einer Funktion zum Programm zurückgegeben werden kann. Das Ziel der Integration der Ausnahmebehandlung ist, die Stabilität des Programms bei Bereitstellung einer Methode zur geordneten Wiederherstellung von einem Fehler zu erhöhen.

## <a name="syntax"></a>Syntax

```cpp
#include <exception>

```

### <a name="typedefs"></a>Typedefs

|Typname|Beschreibung|
|-|-|
|[exception_ptr](../standard-library/exception-typedefs.md#exception_ptr)|Ein Typ, der einen Zeiger auf eine Ausnahme beschreibt.|
|[terminate_handler](../standard-library/exception-typedefs.md#terminate_handler)|Ein Typ, der einen Zeiger auf eine Funktion beschreibt, die zur Verwendung als `terminate_handler` geeignet ist.|
|[unexpected_handler](../standard-library/exception-typedefs.md#unexpected_handler)|Ein Typ, der einen Zeiger auf eine Funktion beschreibt, die zur Verwendung als `unexpected_handler` geeignet ist.|

### <a name="functions"></a>Funktionen

|Funktion|Beschreibung|
|-|-|
|[current_exception](../standard-library/exception-functions.md#current_exception)|Erhält einen Zeiger auf die aktuelle Ausnahme.|
|[get_terminate](../standard-library/exception-functions.md#get_terminate)|Ruft die aktuelle `terminate_handler`-Funktion ab.|
|[get_unexpected](../standard-library/exception-functions.md#get_unexpected)|Ruft die aktuelle `unexpected_handler`-Funktion ab.|
|[make_exception_ptr](../standard-library/exception-functions.md#make_exception_ptr)|Erstellt ein `exception_ptr`-Objekt, das eine Kopie einer Ausnahme enthält.|
|[rethrow_exception](../standard-library/exception-functions.md#rethrow_exception)|Löst eine Ausnahme aus, die als Parameter übergeben wird.|
|[set_terminate](../standard-library/exception-functions.md#set_terminate)|Richtet ein neues `terminate_handler`-Element ein, das bei Beendigung des Programms aufgerufen wird.|
|[set_unexpected](../standard-library/exception-functions.md#set_unexpected)|Richtet ein neues `unexpected_handler` ein, das bei einer unerwarteten Ausnahme auftritt.|
|[terminate](../standard-library/exception-functions.md#terminate)|Ruft einen terminate-Handler auf.|
|[uncaught_exception](../standard-library/exception-functions.md#uncaught_exception)|Gibt nur dann **TRUE** zurück, wenn augenblicklich eine Ausnahme verarbeitet wird.|
|[unexpected](../standard-library/exception-functions.md#unexpected)|Ruft einen unerwarteten Handler auf.|

### <a name="classes"></a>Klassen

|Klasse|Beschreibung|
|-|-|
|[bad_exception-Klasse](../standard-library/bad-exception-class.md)|Die Klasse beschreibt eine Ausnahme, die von `unexpected_handler` ausgelöst werden kann.|
|[exception-Klasse](../standard-library/exception-class.md)|Die Klasse dient als Basisklasse für alle Ausnahmen, die durch spezifische Ausdrücke und die C++-Standardbibliothek ausgelöst werden.|

## <a name="see-also"></a>Siehe auch

[Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)<br/>
[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>

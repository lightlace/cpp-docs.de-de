---
title: '&lt;exception&gt;'
ms.date: 11/04/2016
f1_keywords:
- <exception>
helpviewer_keywords:
- exception header
ms.assetid: 28900768-5dd7-4834-b907-5e37ab3407db
ms.openlocfilehash: 681baee5ac5d19e8b3ffdf37c37599c9cb68f253
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68457904"
---
# <a name="ltexceptiongt"></a>&lt;exception&gt;

Definiert einige Typen und Funktionen, die mit der Behandlung von Ausnahmen in Beziehung stehen. Ausnahmebehandlung wird ist in Situationen verwendet, in denen das System von einem Fehler wiederhergestellt werden kann. Sie stellt eine Methode bereit, mit der die Steuerung von einer Funktion zum Programm zurückgegeben werden kann. Das Ziel der Integration der Ausnahmebehandlung ist, die Stabilität des Programms bei Bereitstellung einer Methode zur geordneten Wiederherstellung von einem Fehler zu erhöhen.

## <a name="requirements"></a>Anforderungen

**Header:** \<exception>

**Namespace:** std

## <a name="members"></a>Member

### <a name="typedefs"></a>Typedefs

|||
|-|-|
|[exception_ptr](../standard-library/exception-typedefs.md#exception_ptr)|Ein Typ, der einen Zeiger auf eine Ausnahme beschreibt.|
|[terminate_handler](../standard-library/exception-typedefs.md#terminate_handler)|Ein Typ, der einen Zeiger auf eine Funktion beschreibt, die zur Verwendung als `terminate_handler` geeignet ist.|
|[unexpected_handler](../standard-library/exception-typedefs.md#unexpected_handler)|Ein Typ, der einen Zeiger auf eine Funktion beschreibt, die zur Verwendung als `unexpected_handler` geeignet ist.|

### <a name="functions"></a>Funktionen

|||
|-|-|
|[current_exception](../standard-library/exception-functions.md#current_exception)|Erhält einen Zeiger auf die aktuelle Ausnahme.|
|[get_terminate](../standard-library/exception-functions.md#get_terminate)|Ruft die aktuelle `terminate_handler`-Funktion ab.|
|[get_unexpected](../standard-library/exception-functions.md#get_unexpected)|Ruft die aktuelle `unexpected_handler`-Funktion ab.|
|[make_exception_ptr](../standard-library/exception-functions.md#make_exception_ptr)|Erstellt ein `exception_ptr`-Objekt, das eine Kopie einer Ausnahme enthält.|
|[rethrow_exception](../standard-library/exception-functions.md#rethrow_exception)|Löst eine Ausnahme aus, die als Parameter übergeben wird.|
|[rethrow_if_nested](../standard-library/exception-functions.md#rethrow_if_nested)|Wandelt eine Ausnahme um, wenn Sie eingefügt wird.|
|[set_terminate](../standard-library/exception-functions.md#set_terminate)|Richtet ein neues `terminate_handler`-Element ein, das bei Beendigung des Programms aufgerufen wird.|
|[set_unexpected](../standard-library/exception-functions.md#set_unexpected)|Richtet ein neues `unexpected_handler` ein, das bei einer unerwarteten Ausnahme auftritt.|
|[terminate](../standard-library/exception-functions.md#terminate)|Ruft einen terminate-Handler auf.|
|[throw_with_nested](../standard-library/exception-functions.md#throw_with_nested)|Löst eine Ausnahme aus, wenn Sie eingefügt wird.|
|[uncaught_exception](../standard-library/exception-functions.md#uncaught_exception)|Gibt nur dann **TRUE** zurück, wenn augenblicklich eine Ausnahme verarbeitet wird.|
|[unexpected](../standard-library/exception-functions.md#unexpected)|Ruft einen unerwarteten Handler auf.|

### <a name="classes"></a>Klassen

|||
|-|-|
|[bad_exception-Klasse](../standard-library/bad-exception-class.md)|Die Klasse beschreibt eine Ausnahme, die von `unexpected_handler` ausgelöst werden kann.|
|[exception-Klasse](../standard-library/exception-class.md)|Die Klasse dient als Basisklasse für alle Ausnahmen, die durch spezifische Ausdrücke und die C++-Standardbibliothek ausgelöst werden.|
|[nested_exception-Klasse](../standard-library/nested-exception-class.md)|Die Klasse beschreibt eine Ausnahme, die für die spätere Verwendung aufgezeichnet und gespeichert werden kann.|

## <a name="see-also"></a>Siehe auch

[Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)\
[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)

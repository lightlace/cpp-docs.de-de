---
title: '&lt;new&gt;'
ms.date: 11/04/2016
f1_keywords:
- <new>
helpviewer_keywords:
- new header
ms.assetid: 218e2a15-34e8-4ef3-9122-1e90eccf8559
ms.openlocfilehash: b6f1cc45f9666fc0fbd2332ac7bb7e539ec77cd3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62223648"
---
# <a name="ltnewgt"></a>&lt;new&gt;

Definiert einige Typen und Funktionen, die die Belegung und Freigabe von Speicher unter Programmsteuerung steuern. Hierin werden außerdem Komponenten für das Berichten von Speicherverwaltungsfehlern definiert.

## <a name="syntax"></a>Syntax

```cpp
#include <new>
```

## <a name="remarks"></a>Hinweise

Einige der Funktionen, die in diesem Header deklariert sind, können ersetzt werden. Die Implementierung stellt eine Standardversion bereit, deren Verhalten in diesem Dokument beschrieben ist. Ein Programm kann jedoch eine Funktion mit derselben Signatur definieren, um die Standardversion zur Linkzeit zu ersetzen. Die ersetzende Version muss die Anforderungen erfüllen, die in diesem Dokument beschrieben sind.

### <a name="objects"></a>erzwingen

|||
|-|-|
|[nothrow](../standard-library/new-functions.md#nothrow)|Stellt ein Objekt als Argument für die **Nothrow** Versionen von **neue** und **löschen**.|

### <a name="typedefs"></a>Typedefs

|Typname|Beschreibung|
|-|-|
|[new_handler](../standard-library/new-typedefs.md#new_handler)|Ein Typ, der auf eine Funktion verweist, die als neuer Handler geeignet ist.|

### <a name="functions"></a>Funktionen

|Funktion|Beschreibung|
|-|-|
|[set_new_handler](../standard-library/new-functions.md#set_new_handler)|Installiert eine Benutzerfunktion, die aufgerufen wird, wenn "new" nicht in der Lage ist, Arbeitsspeicher zu belegen.|

### <a name="operators"></a>Operatoren

|Operator|Beschreibung|
|-|-|
|[operator delete](../standard-library/new-operators.md#op_delete)|Die Funktion, die durch einen Löschausdruck aufgerufen wird, um Speicher für einzelne Objekte freizugeben.|
|[operator delete&#91;&#93;](../standard-library/new-operators.md#op_delete_arr)|Die Funktion, die durch einen Löschausdruck (delete-Ausdruck) aufgerufen wird, um Speicher für ein Array von Objekten freizugeben.|
|[operator new](../standard-library/new-operators.md#op_new)|Die Funktion, die durch einen new-Ausdruck aufgerufen wird, um Speicher für einzelne Objekte zu belegen.|
|[operator new&#91;&#93;](../standard-library/new-operators.md#op_new_arr)|Die Funktion, die durch einen new-Ausdruck aufgerufen wird, um Speicher für ein Array von Objekten zu belegen.|

### <a name="classes"></a>Klassen

|Klasse|Beschreibung|
|-|-|
|[bad_alloc-Klasse](../standard-library/bad-alloc-class.md)|Die Klasse beschreibt eine Ausnahme, die ausgelöst wurde, um anzugeben, dass eine Belegungsanforderung nicht erfolgreich war.|
|[nothrow_t Class (nothrow_t-Klasse)](../standard-library/nothrow-t-structure.md)|Die Klasse wird als Funktionsparameter für den new-Operator verwendet, um anzugeben, dass die Funktion zum Mitteilen eines Belegungsfehlers keine Ausnahme auslösen, sondern einen NULL-Zeiger zurückgeben soll.|

## <a name="see-also"></a>Siehe auch

[Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)<br/>
[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>

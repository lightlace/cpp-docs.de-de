---
title: filesystem_error-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- filesystem/std::experimental::filesystem::filesystem_error
dev_langs:
- C++
ms.assetid: c53aac27-c1fa-43e4-8967-48ea8ba1f172
caps.latest.revision: 13
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: bdc2ba52de6195e737ef6288bac06ac384a8d3e8
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="filesystemerror-class"></a>filesystem_error-Klasse

Eine Basisklasse für alle Ausnahmen, die ausgelöst werden, um einen Systemüberlauf auf niedriger Ebene zu melden.

## <a name="syntax"></a>Syntax

```cpp
class filesystem_error    : public system_error;
```

## <a name="remarks"></a>Hinweise

Die Klasse fungiert als Basisklasse für alle Ausnahmen, die ausgelöst werden, um einen Fehler in \<filesystem>-Funktionen zu melden. Sie speichert ein Objekt vom Typ „string“, das hier zur Veranschaulichung den Namen „mymesg“ erhält. Sie speichert außerdem zwei Objekte vom Typ „path“ namens „mypval1“ und „mypval2“.

## <a name="filesystemerrorfilesystemerror"></a>filesystem_error::filesystem_error

```cpp
filesystem_error(const string& what_arg,
    error_code ec);

filesystem_error(const string& what_arg,
    const path& pval1,
    error_code ec);

filesystem_error(const string& what_arg,
    const path& pval1,
    const path& pval2,
    error_code ec);
```

Der erste Konstruktor erstellt die Meldung aus „what_arg“ und „ec“. Der zweite Konstruktor erstellt die Meldung aus „pval1“, die in „mypval1“ gespeichert wird. Der dritte Konstruktor erstellt die Meldung auch aus „pval1“, die in „mypval1“ gespeichert wird, sowie aus „pval2“, die wiederum in „mypval2“ gespeichert wird.

## <a name="filesystemerrorpath1"></a>filesystem_error::path1

```cpp
const path& path1() const noexcept;
```

Die Memberfunktion gibt „mypval1“ zurück.

## <a name="filesystemerrorpath2"></a>filesystem_error::path2

```cpp
const path& path2() const noexcept;
```

Die Memberfunktion gibt „mypval2“ zurück.

## <a name="filesystemerrorwhat"></a>filesystem_error::what

```cpp
const char *what() const noexcept;
```

Die Memberfunktion gibt einen Zeiger auf ein NTBS zurück, das vorzugsweise aus „runtime_error::what()“, „system_error::what()“, „mymesg“, „mypval1.native_string()“ und „mypval2.native_string()“ besteht.

## <a name="requirements"></a>Anforderungen

**Header:** \<Filesystem >

**Namespace:** std::experimental::filesystem

## <a name="see-also"></a>Siehe auch

[Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)<br/>
[system_error-Klasse](../standard-library/system-error-class.md)<br/>
[\<filesystem>](../standard-library/filesystem.md)<br/>
[\<exception>](../standard-library/exception.md)<br/>

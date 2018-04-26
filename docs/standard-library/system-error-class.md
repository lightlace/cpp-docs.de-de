---
title: system_error-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- system_error/std::system_error
dev_langs:
- C++
helpviewer_keywords:
- system_error class
ms.assetid: 2eeaacbb-8a4a-4ad7-943a-997901a77f32
caps.latest.revision: 17
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e81b4a73067d744745621063ed582dfd59e08581
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="systemerror-class"></a>system_error-Klasse

Stellt die Basisklasse für alle Ausnahmen dar, die ausgelöst werden, um einen Systemfehler auf niedriger Ebene zu melden.

## <a name="syntax"></a>Syntax

```cpp
class system_error : public runtime_error {
public:
    explicit system_error(error_code _Errcode,
    const string& _Message = "");

    system_error(error_code _Errcode,
    const char *_Message);

    system_error(error_code::value_type _Errval,
    const error_category& _Errcat,
    const string& _Message);

    system_error(error_code::value_type _Errval,
    const error_category& _Errcat,
    const char *_Message);
const error_code& code() const throw();
const error_code& code() const throw();

};
```

## <a name="remarks"></a>Hinweise

Der von `what` in der Klasse [exception](../standard-library/exception-class.md) zurückgegebene Wert wird auf der Grundlage von `_Message` und dem gespeicherten Objekt vom Typ [error_code](../standard-library/error-code-class.md) (`code` oder `error_code(_Errval, _Errcat)`) erstellt.

Die Memberfunktion `code` gibt das gespeicherte [error_code](../standard-library/error-code-class.md)-Objekt zurück.

## <a name="requirements"></a>Anforderungen

**Header:** \<system_error>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[<system_error>](../standard-library/system-error.md)<br/>

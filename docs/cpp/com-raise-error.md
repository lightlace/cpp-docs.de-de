---
title: _com_raise_error
ms.date: 11/04/2016
f1_keywords:
- _com_raise_error
helpviewer_keywords:
- _com_raise_error function
ms.assetid: a98226c2-c3fe-44f1-8ff5-85863de11cd6
ms.openlocfilehash: 5790fceef26d6de4edff604270cc7108f764aced
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62399251"
---
# <a name="comraiseerror"></a>_com_raise_error

**Microsoft-spezifisch**

Löst eine [_com_error](../cpp/com-error-class.md) in Reaktion auf einen Fehler.

## <a name="syntax"></a>Syntax

```
void __stdcall _com_raise_error(
   HRESULT hr,
   IErrorInfo* perrinfo = 0
);
```

#### <a name="parameters"></a>Parameter

*hr*<br/>
HRESULT-Informationen.

*perrinfo*<br/>
`IErrorInfo`-Objekt

## <a name="remarks"></a>Hinweise

**_com_raise_error**, definiert in \<comdef.h >, kann durch eine vom Benutzer erstellte Version den gleichen Namen und der Prototyp ersetzt werden. Dies kann ausgeführt werden, wenn Sie `#import` verwenden möchten, jedoch nicht die C++-Ausnahmebehandlung. In diesem Fall kann eine Version **_com_raise_error** könnten Sie eine `longjmp` oder ein Meldungsfeld anzuzeigen und anzuhalten. Die Benutzerversion sollte nicht zurückkehren. Denn die COM-Unterstützung des Compiler-Codes erwartet keine Rückkehr.

Sie können auch [_set_com_error_handler](../cpp/set-com-error-handler.md) ersetzt die Standardfunktion für die Fehlerbehandlung.

In der Standardeinstellung **_com_raise_error** ist wie folgt definiert:

```cpp
void __stdcall _com_raise_error(HRESULT hr, IErrorInfo* perrinfo) {
   throw _com_error(hr, perrinfo);
}
```

**Ende Microsoft-spezifisch**

## <a name="requirements"></a>Anforderungen

**Header:** \<comdef.h>

**Lib:** Wenn die **Wchar_t ist der systemeigene Typ** Compileroption aktiviert ist, verwenden Sie comsuppw.lib oder comsuppwd.lib. Wenn **Wchar_t ist der systemeigene Typ** deaktiviert ist, sollten Sie comsupp.lib verwenden. Weitere Informationen finden Sie unter[/Zc:wchar_t (wchar_t ist der systemeigene Typ)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md).

## <a name="see-also"></a>Siehe auch

[Globale COM-Funktionen des Compilers](../cpp/compiler-com-global-functions.md)<br/>
[_set_com_error_handler](../cpp/set-com-error-handler.md)
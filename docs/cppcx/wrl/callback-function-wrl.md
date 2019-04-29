---
title: Callback-Funktion (WRL)
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::Callback
ms.assetid: afb15d25-3230-44f7-b321-e17c54872943
ms.openlocfilehash: d37e6fdd2521f07728305bfbf5441cebb363030a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62398900"
---
# <a name="callback-function-wrl"></a>Callback-Funktion (WRL)

Erstellt ein Objekt, dessen Memberfunktion eine Rückrufmethode ist.

## <a name="syntax"></a>Syntax

```cpp
template<
   typename TDelegateInterface,
   typename TCallback
>
ComPtr<TDelegateInterface> Callback(
   TCallbackcallback
);
template<
   typename TDelegateInterface,
   typename TCallbackObject
>
ComPtr<TDelegateInterface> Callback(
   _In_ TCallbackObject *object,
   _In_ HRESULT (TCallbackObject::* method)()
);
template<
   typename TDelegateInterface,
   typename TCallbackObject,
   typename TArg1
>
ComPtr<TDelegateInterface> Callback(
   _In_ TCallbackObject *object,
   _In_ HRESULT (TCallbackObject::* method)(TArg1)
);
template<
   typename TDelegateInterface,
   typename TCallbackObject,
   typename TArg1,
   typename TArg2
>
ComPtr<TDelegateInterface> Callback(
   _In_ TCallbackObject *object,
   _In_ HRESULT (TCallbackObject::* method)(TArg1,
   TArg2)
);
template<
   typename TDelegateInterface,
   typename TCallbackObject,
   typename TArg1,
   typename TArg2,
   typename TArg3
>
ComPtr<TDelegateInterface> Callback(
   _In_ TCallbackObject *object,
   _In_ HRESULT (TCallbackObject::* method)(TArg1,
   TArg2,
   TArg3)
);
template<
   typename TDelegateInterface,
   typename TCallbackObject,
   typename TArg1,
   typename TArg2,
   typename TArg3,
   typename TArg4
>
ComPtr<TDelegateInterface> Callback(
   _In_ TCallbackObject *object,
   _In_ HRESULT (TCallbackObject::* method)(TArg1,
   TArg2,
   TArg3,
   TArg4)
);
template<
   typename TDelegateInterface,
   typename TCallbackObject,
   typename TArg1,
   typename TArg2,
   typename TArg3,
   typename TArg4,
   typename TArg5
>
ComPtr<TDelegateInterface> Callback(
   _In_ TCallbackObject *object,
   _In_ HRESULT (TCallbackObject::* method)(TArg1,
   TArg2,
   TArg3,
   TArg4,
   TArg5)
);
template<
   typename TDelegateInterface,
   typename TCallbackObject,
   typename TArg1,
   typename TArg2,
   typename TArg3,
   typename TArg4,
   typename TArg5,
   typename TArg6
>
ComPtr<TDelegateInterface> Callback(
   _In_ TCallbackObject *object,
   _In_ HRESULT (TCallbackObject::* method)(TArg1,
   TArg2,
   TArg3,
   TArg4,
   TArg5,
   TArg6)
);
template<
   typename TDelegateInterface,
   typename TCallbackObject,
   typename TArg1,
   typename TArg2,
   typename TArg3,
   typename TArg4,
   typename TArg5,
   typename TArg6,
   typename TArg7
>
ComPtr<TDelegateInterface> Callback(
   _In_ TCallbackObject *object,
   _In_ HRESULT (TCallbackObject::* method)(TArg1,
   TArg2,
   TArg3,
   TArg4,
   TArg5,
   TArg6,
   TArg7)
);
template<
   typename TDelegateInterface,
   typename TCallbackObject,
   typename TArg1,
   typename TArg2,
   typename TArg3,
   typename TArg4,
   typename TArg5,
   typename TArg6,
   typename TArg7,
   typename TArg8
>
ComPtr<TDelegateInterface> Callback(
   _In_ TCallbackObject *object,
   _In_ HRESULT (TCallbackObject::* method)(TArg1,
   TArg2,
   TArg3,
   TArg4,
   TArg5,
   TArg6,
   TArg7,
   TArg8)
);
template<
   typename TDelegateInterface,
   typename TCallbackObject,
   typename TArg1,
   typename TArg2,
   typename TArg3,
   typename TArg4,
   typename TArg5,
   typename TArg6,
   typename TArg7,
   typename TArg8,
   typename TArg9
>
ComPtr<TDelegateInterface> Callback(
   _In_ TCallbackObject *object,
   _In_ HRESULT (TCallbackObject::* method)(TArg1,
   TArg2,
   TArg3,
   TArg4,
   TArg5,
   TArg6,
   TArg7,
   TArg8,
   TArg9)
);
```

### <a name="parameters"></a>Parameter

*TDelegateInterface*<br/>
Ein Vorlagenparameter, der die Schnittstelle des Delegaten angibt, der beim Eintreten eines Ereignisses aufgerufen wird.

*TCallback*<br/>
Ein Vorlagenparameter, der den Typ eines Objekts angibt, das ein Objekt und seine Rückrufmemberfunktion darstellt.

*TCallbackObject*<br/>
Ein Vorlagenparameter, der das Objekt angibt, dessen Memberfunktion die Methode ist, die beim Eintreten eines Ereignisses aufgerufen wird.

*TArg1*<br/>
Ein Vorlagenparameter, der den Typ des ersten Rückrufmethodenarguments angibt.

*TArg2*<br/>
Ein Vorlagenparameter, der den Typ des zweiten Rückrufmethodenarguments angibt.

*TArg3*<br/>
Ein Vorlagenparameter, der den Typ des dritten Rückrufmethodenarguments angibt.

*TArg4*<br/>
Ein Vorlagenparameter, der den Typ des vierten Rückrufmethodenarguments angibt.

*TArg5*<br/>
Ein Vorlagenparameter, der den Typ des fünften Rückrufmethodenarguments angibt.

*TArg6*<br/>
Ein Vorlagenparameter, der den Typ des sechsten Rückrufmethodenarguments angibt.

*TArg7*<br/>
Ein Vorlagenparameter, der den Typ des siebten Rückrufmethodenarguments angibt.

*TArg8*<br/>
Ein Vorlagenparameter, der den Typ des achten Rückrufmethodenarguments angibt.

*TArg9*<br/>
Ein Vorlagenparameter, der den Typ des neunten Rückrufmethodenarguments angibt.

*callback*<br/>
Ein Objekt, das das Rückrufobjekt und seine Memberfunktion darstellt.

*object*<br/>
Das Objekt, dessen Memberfunktion beim Eintreten eines Ereignisses aufgerufen wird.

*method*<br/>
Die Memberfunktion, die beim Eintreten eines Ereignisses aufgerufen wird.

## <a name="return-value"></a>Rückgabewert

Ein Objekt, dessen Memberfunktion die angegebene Rückrufmethode ist.

## <a name="remarks"></a>Hinweise

Die Basis eines Delegatobjekts muss `IUnknown`, nicht `IInspectable`.

## <a name="requirements"></a>Anforderungen

**Header:** event.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Siehe auch

[Microsoft::WRL-Namespace](microsoft-wrl-namespace.md)
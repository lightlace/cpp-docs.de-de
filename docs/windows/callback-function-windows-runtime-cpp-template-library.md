---
title: Rückruffunktion (Windows Runtime C++-Vorlagenbibliothek) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::Callback
dev_langs:
- C++
ms.assetid: afb15d25-3230-44f7-b321-e17c54872943
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 27d89f60f27c71cec0f158375805e3e8487fd7a6
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
---
# <a name="callback-function-windows-runtime-c-template-library"></a>Rückruffunktion (C++-Vorlagenbibliothek der Windows-Runtime)
Erstellt ein Objekt, dessen Memberfunktion eine Rückrufmethode ist.  
  
## <a name="syntax"></a>Syntax  
  
```  
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
  
#### <a name="parameters"></a>Parameter  
 `TDelegateInterface`  
 Ein Vorlagenparameter, der die Schnittstelle des Delegaten angibt, der beim Eintreten eines Ereignisses aufgerufen wird.  
  
 `TCallback`  
 Ein Vorlagenparameter, der den Typ eines Objekts angibt, das ein Objekt und seine Rückrufmemberfunktion darstellt.  
  
 `TCallbackObject`  
 Ein Vorlagenparameter, der das Objekt angibt, dessen Memberfunktion die Methode ist, die beim Eintreten eines Ereignisses aufgerufen wird.  
  
 `TArg1`  
 Ein Vorlagenparameter, der den Typ des ersten Rückrufmethodenarguments angibt.  
  
 `TArg2`  
 Ein Vorlagenparameter, der den Typ des zweiten Rückrufmethodenarguments angibt.  
  
 `TArg3`  
 Ein Vorlagenparameter, der den Typ des dritten Rückrufmethodenarguments angibt.  
  
 `TArg4`  
 Ein Vorlagenparameter, der den Typ des vierten Rückrufmethodenarguments angibt.  
  
 `TArg5`  
 Ein Vorlagenparameter, der den Typ des fünften Rückrufmethodenarguments angibt.  
  
 `TArg6`  
 Ein Vorlagenparameter, der den Typ des sechsten Rückrufmethodenarguments angibt.  
  
 `TArg7`  
 Ein Vorlagenparameter, der den Typ des siebten Rückrufmethodenarguments angibt.  
  
 `TArg8`  
 Ein Vorlagenparameter, der den Typ des achten Rückrufmethodenarguments angibt.  
  
 `TArg9`  
 Ein Vorlagenparameter, der den Typ des neunten Rückrufmethodenarguments angibt.  
  
 `callback`  
 Ein Objekt, das das Rückrufobjekt und seine Memberfunktion darstellt.  
  
 `object`  
 Das Objekt, dessen Memberfunktion beim Eintreten eines Ereignisses aufgerufen wird.  
  
 `method`  
 Die Memberfunktion, die beim Eintreten eines Ereignisses aufgerufen wird.  
  
## <a name="return-value"></a>Rückgabewert  
 Ein Objekt, dessen Memberfunktion die angegebene Rückrufmethode ist.  
  
## <a name="remarks"></a>Hinweise  
 Die Basis eines Delegatobjekts muss "IUnknown" und nicht "IInspectable" lauten.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** event.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Siehe auch  
 [Microsoft::WRL-Namespace](../windows/microsoft-wrl-namespace.md)
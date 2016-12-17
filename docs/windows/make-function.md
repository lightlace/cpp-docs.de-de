---
title: "Make-Funktion"
ms.custom: na
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
f1_keywords: 
  - "implements/Microsoft::WRL::Make"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Make-Funktion"
ms.assetid: 66704143-df99-4a95-904d-ed99607e1034
caps.latest.revision: 4
caps.handback.revision: "4"
ms.author: "mblome"
manager: "ghogen"
---
# Make-Funktion
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Initialisiert die angegebene [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]\-Klasse.  Verwenden Sie diese Funktion, um eine Komponente zu instanziieren, die in demselben Modul definiert ist.  
  
## Syntax  
  
```  
template <  
   typename T,  
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
ComPtr<T> Make(  
   TArg1 &&arg1,  
   TArg2 &&arg2,  
   TArg3 &&arg3,  
   TArg4 &&arg4,  
   TArg5 &&arg5,  
   TArg6 &&arg6,  
   TArg7 &&arg7,  
   TArg8 &&arg8,  
   TArg9 &&arg9  
);  
template <  
   typename T,  
   typename TArg1,  
   typename TArg2,  
   typename TArg3,  
   typename TArg4,  
   typename TArg5,  
   typename TArg6,  
   typename TArg7,  
   typename TArg8  
>  
ComPtr<T> Make(  
   TArg1 &&arg1,  
   TArg2 &&arg2,  
   TArg3 &&arg3,  
   TArg4 &&arg4,  
   TArg5 &&arg5,  
   TArg6 &&arg6,  
   TArg7 &&arg7,  
   TArg8 &&arg8  
);  
template <  
   typename T,  
   typename TArg1,  
   typename TArg2,  
   typename TArg3,  
   typename TArg4,  
   typename TArg5,  
   typename TArg6,  
   typename TArg7  
>  
ComPtr<T> Make(  
   TArg1 &&arg1,  
   TArg2 &&arg2,  
   TArg3 &&arg3,  
   TArg4 &&arg4,  
   TArg5 &&arg5,  
   TArg6 &&arg6,  
   TArg7 &&arg7  
);  
template <  
   typename T,  
   typename TArg1,  
   typename TArg2,  
   typename TArg3,  
   typename TArg4,  
   typename TArg5,  
   typename TArg6  
>  
ComPtr<T> Make(  
   TArg1 &&arg1,  
   TArg2 &&arg2,  
   TArg3 &&arg3,  
   TArg4 &&arg4,  
   TArg5 &&arg5,  
   TArg6 &&arg6  
);  
template <  
   typename T,  
   typename TArg1,  
   typename TArg2,  
   typename TArg3,  
   typename TArg4,  
   typename TArg5  
>  
ComPtr<T> Make(  
   TArg1 &&arg1,  
   TArg2 &&arg2,  
   TArg3 &&arg3,  
   TArg4 &&arg4,  
   TArg5 &&arg5  
);  
template <  
   typename T,  
   typename TArg1,  
   typename TArg2,  
   typename TArg3,  
   typename TArg4  
>  
ComPtr<T> Make(  
   TArg1 &&arg1,  
   TArg2 &&arg2,  
   TArg3 &&arg3,  
   TArg4 &&arg4  
);  
template <  
   typename T,  
   typename TArg1,  
   typename TArg2,  
   typename TArg3  
>  
ComPtr<T> Make(  
   TArg1 &&arg1,  
   TArg2 &&arg2,  
   TArg3 &&arg3  
);  
template <  
   typename T,  
   typename TArg1,  
   typename TArg2  
>  
ComPtr<T> Make(  
   TArg1 &&arg1,  
   TArg2 &&arg2  
);  
template <  
   typename T,  
   typename TArg1  
>  
ComPtr<T> Make(  
   TArg1 &&arg1  
);  
template <  
   typename T  
>  
ComPtr<T> Make();  
```  
  
#### Parameter  
 `T`  
 Eine vom Benutzer angegebene Klasse, die von `WRL::RuntimeClass` erbt.  
  
 `TArg1`  
 Typ vom Argument 1, das der angegebenen Laufzeitklasse übergeben wird.  
  
 `TArg2`  
 Typ vom Argument 2, das der angegebenen Laufzeitklasse übergeben wird.  
  
 `TArg3`  
 Typ vom Argument 3, das der angegebenen Laufzeitklasse übergeben wird.  
  
 `TArg4`  
 Typ vom Argument 4, das der angegebenen Laufzeitklasse übergeben wird.  
  
 `TArg5`  
 Typ vom Argument 5, das der angegebenen Laufzeitklasse übergeben wird.  
  
 `TArg6`  
 Typ vom Argument 6, das der angegebenen Laufzeitklasse übergeben wird.  
  
 `TArg7`  
 Typ vom Argument 7, das der angegebenen Laufzeitklasse übergeben wird.  
  
 `TArg8`  
 Typ vom Argument 8, das der angegebenen Laufzeitklasse übergeben wird.  
  
 `TArg9`  
 Typ vom Argument 9, das der angegebenen Laufzeitklasse übergeben wird.  
  
 `arg1`  
 Argument 1, das der angegebenen Laufzeitklasse übergeben wird.  
  
 `arg2`  
 Argument 2, das der angegebenen Laufzeitklasse übergeben wird.  
  
 `arg3`  
 Argument 3, das der angegebenen Laufzeitklasse übergeben wird.  
  
 `arg4`  
 Argument 4, das der angegebenen Laufzeitklasse übergeben wird.  
  
 `arg5`  
 Argument 5, das der angegebenen Laufzeitklasse übergeben wird.  
  
 `arg6`  
 Argument 6, das der angegebenen Laufzeitklasse übergeben wird.  
  
 `arg7`  
 Argument 7, das der angegebenen Laufzeitklasse übergeben wird.  
  
 `arg8`  
 Argument 8, das der angegebenen Laufzeitklasse übergeben wird.  
  
 `arg9`  
 Argument 9, das der angegebenen Laufzeitklasse übergeben wird.  
  
## Rückgabewert  
 Ein `ComPtr<T>`\-Objekt, wenn erfolgreich; andernfalls `nullptr`.  
  
## Hinweise  
 Siehe [Gewusst wie: Direktes Instanziieren von WRL\-Komponenten](../windows/how-to-instantiate-wrl-components-directly.md), um die Unterschiede zwischen dieser Funktion und [Microsoft::WRL::Details::MakeAndInitialize](../windows/makeandinitialize-function.md) zu erfahren und ein Beispiel.  
  
## Anforderungen  
 **Header:** implements.h  
  
 **Namespace:** Microsoft::WRL  
  
## Siehe auch  
 [Microsoft::WRL\-Namespace](../windows/microsoft-wrl-namespace.md)
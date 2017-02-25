---
title: "ComPtr::As-Methode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "client/Microsoft::WRL::ComPtr::As"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "As-Methode"
ms.assetid: 2ad6c262-9bdb-4c59-a330-1af8bcd445cc
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# ComPtr::As-Methode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Gibt ein ComPtr-Objekt zurück, das die Schnittstelle darstellt, die durch den angegebenen Vorlagenparameter gekennzeichnet ist.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
template<  
   typename U  
>  
HRESULT As(  
   _Out_ ComPtr<U>* p  
) const;  
  
template<  
   typename U  
>  
HRESULT As(  
   _Out_ Details::ComPtrRef<ComPtr<U>> p  
) const;  
  
```  
  
#### <a name="parameters"></a>Parameter  
 `U`  
 Die Schnittstelle, die vom Parameter dargestellt werden `p`.  
  
 `p`  
 Ein ComPtr-Objekt, das vom Parameter angegebene Schnittstelle stellt `U`. Parameter `p` muss nicht mit dem aktuellen ComPtr-Objekt verweisen.  
  
## <a name="remarks"></a>Hinweise  
 Die erste Vorlage ist die Form, die Sie in Ihrem Code verwenden sollten. Die zweite Vorlage ist eine interne Hilfsmethode Spezialisierung, die Features der Programmiersprache C++, z. B. unterstützt die [Auto](../cpp/auto-cpp.md) typableitungsschlüsselwort.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn erfolgreich; andernfalls ein HRESULT, das den Fehler angibt.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** client.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Siehe auch  
 [ComPtr-Klasse](../windows/comptr-class.md)
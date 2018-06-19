---
title: 'Marshal_context:: ~ Marshal_context | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- marshal_context::~marshal_context
- msclr.interop.marshal_context.~marshal_context
- marshal_context.~marshal_context
- msclr::interop::marshal_context::~marshal_context
- ~marshal_context
dev_langs:
- C++
helpviewer_keywords:
- marshal_context class [C++], operations
ms.assetid: 34c41b38-4c33-4f61-b74e-831ac46b4ab5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: a6cb7ed3c7b1ee5b28c4943d83b6a8ca6166b6d0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33138087"
---
# <a name="marshalcontextmarshalcontext"></a>marshal_context::~marshal_context
Zerstört ein `marshal_context`-Objekt.  
  
## <a name="syntax"></a>Syntax  
  
```  
~marshal_context();  
```  
  
## <a name="remarks"></a>Hinweise  
 Einige datenkonvertierungen erfordern einen Kontext gemarshallt. Finden Sie unter [Overview of Marshaling in C++](../dotnet/overview-of-marshaling-in-cpp.md) erfahren, welche Übersetzungen einen Kontext benötigen und welche Marshalling Datei hat, in der Anwendung eingeschlossen werden sollen.  
  
 Löschen einer `marshal_context` Objekt werden die Daten konvertiert, die von diesem Kontext ungültig. Wenn Sie Ihre Daten nach dem beibehalten möchten eine `marshal_context` -Objekt zerstört wird, müssen Sie die Daten manuell kopieren, auf eine Variable, die beibehalten wird.  
  
## <a name="requirements"></a>Anforderungen  
 **Headerdatei:** \<msclr\marshal.h >, \<msclr\marshal_windows.h >, \<msclr\marshal_cppstd.h >, oder \<msclr\marshal_atl.h >  
  
 **Namespace:** msclr::interop  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über das Marshaling in C++](../dotnet/overview-of-marshaling-in-cpp.md)   
 [marshal_as](../dotnet/marshal-as.md)   
 [marshal_context-Klasse](../dotnet/marshal-context-class.md)
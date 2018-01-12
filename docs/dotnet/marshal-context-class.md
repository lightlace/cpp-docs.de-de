---
title: Marshal_context-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: marshal_context
dev_langs: C++
helpviewer_keywords: marshal_context class [C++]
ms.assetid: 241b0cf6-4ca4-4812-aaee-d671c11dc034
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 9b59dfa82563a0c115f521bb881411981a30efc9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="marshalcontext-class"></a>marshal_context-Klasse
Diese Klasse konvertiert die Daten zwischen systemeigenen und verwalteten Umgebungen.  
  
## <a name="syntax"></a>Syntax  
  
```  
class marshal_context  
```  
  
## <a name="remarks"></a>Hinweise  
 Verwenden der `marshal_context` Klasse für die Konvertierung von Daten, die einen Kontext benötigen. Finden Sie unter [Overview of Marshaling in C++](../dotnet/overview-of-marshaling-in-cpp.md) erfahren, welche Konvertierungen einen Kontext benötigen und welche Marshalling-Datei enthalten sein muss. Das Ergebnis des Marshallens bei der Verwendung von eines Kontexts ist gültig, bis die `marshal_context` -Objekt zerstört wird. Um Ihr Ergebnis zu erhalten, müssen Sie die Daten kopieren.  
  
 Die gleiche `marshal_context` für mehrere datenkonvertierungen verwendet werden kann. Wiederverwenden von Kontext auf diese Weise wirkt sich nicht auf die Ergebnisse der vorherigen Marshalling aufrufen.  
  
## <a name="requirements"></a>Anforderungen  
 **Headerdatei:** \<msclr\marshal.h >, \<msclr\marshal_windows.h >, \<msclr\marshal_cppstd.h >, oder \<msclr\marshal_atl.h >  
  
 **Namespace:** msclr::interop  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über das Marshaling in C++](../dotnet/overview-of-marshaling-in-cpp.md)   
 [marshal_as](../dotnet/marshal-as.md)
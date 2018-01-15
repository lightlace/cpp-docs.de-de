---
title: bad_exception-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: exception/std::bad_exception
dev_langs: C++
helpviewer_keywords: bad_exception class
ms.assetid: 5ae2c4ef-c7ad-4469-8a9e-a773e86bb000
caps.latest.revision: "20"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b5b91f3019a46aa011f95ae26434456d1e41de08
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="badexception-class"></a>bad_exception-Klasse
Die Klasse beschreibt eine Ausnahme, die von einem unexpected-Handler ausgelöst werden kann.  
  
## <a name="syntax"></a>Syntax  
  
```  
class bad_exception    : public exception {};  
```  
  
## <a name="remarks"></a>Hinweise  
 [unexpected](../standard-library/exception-functions.md#unexpected) löst `bad_exception` aus, anstatt zu terminieren oder eine andere mit [set_unexpected](../standard-library/exception-functions.md#set_unexpected) angegebene Funktion aufzurufen, wenn `bad_exception` in der Auslöseliste einer Funktion enthalten ist.  
  
 Der von **what** zurückgegebene Wert ist eine durch die Implementierung definierte C-Zeichenfolge. Keine der Memberfunktionen löst irgendeine Ausnahme aus.  
  
 Sie finden eine Liste der Member, die von der `bad_exception`-Klasse geerbt werden, unter [exception-Klasse](../standard-library/exception-class.md).  
  
## <a name="example"></a>Beispiel  
 Ein Beispiel zur Verwendung von [unexpected](../standard-library/exception-functions.md#unexpected), das `bad_exception` auslöst, finden Sie unter [set_unexpected](../standard-library/exception-functions.md#set_unexpected).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<exception>  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Siehe auch  
[Exception-Klasse](../standard-library/exception-class.md) [Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)


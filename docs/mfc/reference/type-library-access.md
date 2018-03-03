---
title: Geben Sie Bibliothekszugriff | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.macros
dev_langs:
- C++
helpviewer_keywords:
- type libraries [MFC], accessing
ms.assetid: a03fa7f0-86c2-4119-bf81-202916fb74b3
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: bbc5ceabe60d7ee15d85495bb1a431955a589849
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="type-library-access"></a>Zugreifen auf die Typbibliothek
Typbibliotheken verfügbar machen, die Schnittstellen eines OLE-Steuerelements an andere OLE-fähigen Anwendungen. Jeder OLE-Steuerelements benötigen eine Typbibliothek aus, wenn eine oder mehrere Schnittstellen verfügbar gemacht werden sollen.  
  
 Die folgenden Makros zulassen ein OLE-Steuerelements für den Zugriff auf eine eigene Typbibliothek:  
  
### <a name="type-library-access"></a>Zugreifen auf die Typbibliothek  
  
|||  
|-|-|  
|[DECLARE_OLETYPELIB](#declare_oletypelib)|Deklariert eine `GetTypeLib` Memberfunktion eines OLE-Steuerelements (muss in der Klassendeklaration verwendet werden).|  
|[IMPLEMENT_OLETYPELIB](#implement_oletypelib)|Implementiert eine `GetTypeLib` Memberfunktion eines OLE-Steuerelements (muss in der klassenimplementierung verwendet werden).|  
  
##  <a name="declare_oletypelib"></a>DECLARE_OLETYPELIB  
 Deklariert die `GetTypeLib` Memberfunktion der Control-Klasse.  
  
```   
DECLARE_OLETYPELIB(class_name)   
```  
  
### <a name="parameters"></a>Parameter  
 *CLASS_NAME*  
 Der Name des der Control-Klasse, die im Zusammenhang mit der Typbibliothek.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie dieses Makro in der Headerdatei des Steuerelements-Klasse.  

### <a name="requirements"></a>Anforderungen  
 **Header:** afxdisp.h  

##  <a name="implement_oletypelib"></a>IMPLEMENT_OLETYPELIB  
 Des Steuerelements implementiert `GetTypeLib` Memberfunktion.  
  
```   
IMPLEMENT_OLETYPELIB(class_name, tlid, wVerMajor,  wVerMinor)   
```  
  
### <a name="parameters"></a>Parameter  
 *CLASS_NAME*  
 Der Name des der Control-Klasse, die im Zusammenhang mit der Typbibliothek.  
  
 *tlid*  
 Die ID der Typbibliothek.  
  
 `wVerMajor`  
 Die Typ-Bibliothek Hauptversionsnummer.  
  
 `wVerMinor`  
 Die Typ-Bibliothek Nebenversionsnummer.  
  
### <a name="remarks"></a>Hinweise  
 Dieses Makro muss angezeigt werden, in der Implementierungsdatei für alle Control-Klasse, verwendet die `DECLARE_OLETYPELIB` Makro.  

### <a name="requirements"></a>Anforderungen  
 **Header:** afxdisp.h  
   
## <a name="see-also"></a>Siehe auch  
 [Makros und globale Variablen](../../mfc/reference/mfc-macros-and-globals.md)

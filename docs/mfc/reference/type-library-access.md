---
title: Geben Sie Bibliothekszugriff | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.mfc.macros
dev_langs:
- C++
helpviewer_keywords:
- type libraries [MFC], accessing
ms.assetid: a03fa7f0-86c2-4119-bf81-202916fb74b3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fb81a8aa7d9262992da29a2d93cf770fad754316
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33373210"
---
# <a name="type-library-access"></a>Zugreifen auf die Typbibliothek
Typbibliotheken verfügbar machen, die Schnittstellen eines OLE-Steuerelements an andere OLE-fähigen Anwendungen. Jeder OLE-Steuerelements benötigen eine Typbibliothek aus, wenn eine oder mehrere Schnittstellen verfügbar gemacht werden sollen.  
  
 Die folgenden Makros zulassen ein OLE-Steuerelements für den Zugriff auf eine eigene Typbibliothek:  
  
### <a name="type-library-access"></a>Zugreifen auf die Typbibliothek  
  
|||  
|-|-|  
|[DECLARE_OLETYPELIB](#declare_oletypelib)|Deklariert eine `GetTypeLib` Memberfunktion eines OLE-Steuerelements (muss in der Klassendeklaration verwendet werden).|  
|[IMPLEMENT_OLETYPELIB](#implement_oletypelib)|Implementiert eine `GetTypeLib` Memberfunktion eines OLE-Steuerelements (muss in der klassenimplementierung verwendet werden).|  
  
##  <a name="declare_oletypelib"></a>  DECLARE_OLETYPELIB  
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

##  <a name="implement_oletypelib"></a>  IMPLEMENT_OLETYPELIB  
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

---
title: Geben Sie Zugriff auf die Medienbibliothek | Microsoft-Dokumentation
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
- type libraries, accessing
ms.assetid: a03fa7f0-86c2-4119-bf81-202916fb74b3
caps.latest.revision: 14
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 17a158366f94d27b7a46917282425d652e6b9042
ms.openlocfilehash: 8a3fbcf66036ef3df3bd34b5182dac8af3dfccef
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="type-library-access"></a>Zugreifen auf die Typbibliothek
Typbibliotheken verfügbar machen, die Schnittstellen eines OLE-Steuerelements an andere OLE-kompatible Anwendung. Jedes Steuerelement OLE benötigen eine Typbibliothek aus, wenn eine oder mehrere Schnittstellen verfügbar gemacht werden sollen.  
  
 Die folgenden Makros zulassen ein OLE-Steuerelements Zugriff auf eigenen Typbibliothek:  
  
### <a name="type-library-access"></a>Zugreifen auf die Typbibliothek  
  
|||  
|-|-|  
|[DECLARE_OLETYPELIB](#declare_oletypelib)|Deklariert einen `GetTypeLib` -Memberfunktion eines OLE-Steuerelements (muss in der Klassendeklaration verwendet werden).|  
|[IMPLEMENT_OLETYPELIB](#implement_oletypelib)|Implementiert eine `GetTypeLib` -Memberfunktion eines OLE-Steuerelements (muss in der klassenimplementierung verwendet werden).|  
  
##  <a name="declare_oletypelib"></a>DECLARE_OLETYPELIB  
 Deklariert die `GetTypeLib` -Memberfunktion der Steuerelementklasse.  
  
```   
DECLARE_OLETYPELIB(class_name)   
```  
  
### <a name="parameters"></a>Parameter  
 *CLASS_NAME*  
 Der Name von der Control-Klasse, die im Zusammenhang mit der Typbibliothek.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie dieses Makro in der Headerdatei der Control-Klasse.  

### <a name="requirements"></a>Anforderungen  
 **Header:** afxdisp.h  

##  <a name="implement_oletypelib"></a>IMPLEMENT_OLETYPELIB  
 Implementiert das Steuerelement `GetTypeLib` Member-Funktion.  
  
```   
IMPLEMENT_OLETYPELIB(class_name, tlid, wVerMajor,  wVerMinor)   
```  
  
### <a name="parameters"></a>Parameter  
 *CLASS_NAME*  
 Der Name von der Control-Klasse, die im Zusammenhang mit der Typbibliothek.  
  
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


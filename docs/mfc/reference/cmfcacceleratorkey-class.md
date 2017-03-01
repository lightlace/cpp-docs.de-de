---
title: Klasse CMFCAcceleratorKey | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCAcceleratorKey
dev_langs:
- C++
helpviewer_keywords:
- CMFCAcceleratorKey class
ms.assetid: d140fbf7-23db-45ea-a63e-414a5ec7b3d5
caps.latest.revision: 36
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
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 7baa210acfabe8f17e2ab747fd98fe463c2907a2
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcacceleratorkey-class"></a>CMFCAcceleratorKey-Klasse
Eine Hilfsklasse, die virtuelle tastenzuordnung und Formatierung implementiert.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCAcceleratorKey : public CObject  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCAcceleratorKey::CMFCAcceleratorKey](#cmfcacceleratorkey)|Erstellt ein `CMFCAcceleratorKey`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCAcceleratorKey::Format](#format)|Übersetzt die ZUGRIFFSTASTE-Struktur, die die visuelle Darstellung.|  
|[CMFCAcceleratorKey::SetAccelerator](#setaccelerator)|Legt die Tastenkombination für das `CMFCAcceleratorKey` Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 Zugriffstasten werden auch bezeichnet als Tastenkombinationen. Wenn Sie möchten, um Tastenkombinationen anzuzeigen, die ein Benutzer eingibt, die [CMFCAcceleratorKeyAssignCtrl Klasse](../../mfc/reference/cmfcacceleratorkeyassignctrl-class.md) Maps Tastenkombinationen, z. B. Alt + Umschalt + S, um einen benutzerdefinierten Text-Format, z. B. "Alt + Umschalt + S". Jede `CMFCAcceleratorKey` -Objekt ordnet eine einzelnen Tastenkombination in ein Textformat.  
  
 Weitere Informationen zur Verwendung von Tastenkombinationen und Zugriffstastentabellen finden Sie unter [CKeyboardManager Klasse](../../mfc/reference/ckeyboardmanager-class.md).  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht das Erstellen einer `CMFCAcceleratorKey` -Objekt und zum Verwenden der `Format` Methode.  
  
 [!code-cpp[NVC_MFC_RibbonApp&#30;](../../mfc/reference/codesnippet/cpp/cmfcacceleratorkey-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 `CMFCAcceleratorKey`   
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxacceleratorkey.h  
  
##  <a name="a-namecmfcacceleratorkeya--cmfcacceleratorkeycmfcacceleratorkey"></a><a name="cmfcacceleratorkey"></a>CMFCAcceleratorKey::CMFCAcceleratorKey  
 Erstellt eine [CMFCAcceleratorKey](../../mfc/reference/cmfcacceleratorkey-class.md) Objekt.  
  
```  
CMFCAcceleratorKey();  
CMFCAcceleratorKey(LPACCEL lpAccel);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpAccel`  
 Ein Zeiger auf eine Tastenkombination.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie eine Tastenkombination nicht angeben, bei der Erstellung einer `CMFCAccleratorKey`, verwenden Sie die [CMFCAcceleratorKey::SetAccelerator](#setaccelerator) Methode, um eine Tastenkombination zuordnen Ihrer `CMFCAcceleratorKey` Objekt.  
  
##  <a name="a-nameformata--cmfcacceleratorkeyformat"></a><a name="format"></a>CMFCAcceleratorKey::Format  
 Übersetzt die ZUGRIFFSTASTE-Struktur, die den zugeordneten Wert an.  
  
```  
void Format(CString& str) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [out] `str`  
 Ein Verweis auf ein `CString` Objekt, in dem die Methode die übersetzte Tastenkombination schreibt.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode ruft das Format der zugeordnete Tastenkombination ab. Sie können das Zeichenfolgenformat Festlegen einer [CMFCAcceleratorKey](../../mfc/reference/cmfcacceleratorkey-class.md) -Objekt mit dem Konstruktor oder die Methode [CMFCAcceleratorKey::SetAccelerator](#setaccelerator).  
  
##  <a name="a-namesetacceleratora--cmfcacceleratorkeysetaccelerator"></a><a name="setaccelerator"></a>CMFCAcceleratorKey::SetAccelerator  
 Legt die Tastenkombination für das [CMFCAcceleratorKey](../../mfc/reference/cmfcacceleratorkey-class.md) Objekt.  
  
```  
void SetAccelerator(LPACCEL lpAccel);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpAccel`  
 Ein Zeiger auf eine Tastenkombination.  
  
### <a name="remarks"></a>Hinweise  
 Mit dieser Methode können Sie die Tastenkombination festlegen einer `CMFCAcceleratorKey` Wenn Sie eine Tastenkombination nicht bereitgestellt haben, bei der Erstellung der `CMFCAcceleratorKey`.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CKeyboardManager-Klasse](../../mfc/reference/ckeyboardmanager-class.md)


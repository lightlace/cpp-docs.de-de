---
title: CMFCAcceleratorKey-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCAcceleratorKey
- AFXACCELERATORKEY/CMFCAcceleratorKey
- AFXACCELERATORKEY/CMFCAcceleratorKey::CMFCAcceleratorKey
- AFXACCELERATORKEY/CMFCAcceleratorKey::Format
- AFXACCELERATORKEY/CMFCAcceleratorKey::SetAccelerator
dev_langs: C++
helpviewer_keywords:
- CMFCAcceleratorKey [MFC], CMFCAcceleratorKey
- CMFCAcceleratorKey [MFC], Format
- CMFCAcceleratorKey [MFC], SetAccelerator
ms.assetid: d140fbf7-23db-45ea-a63e-414a5ec7b3d5
caps.latest.revision: "36"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3303be9f37749436d140028cd5fa45cd4454c8c8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="cmfcacceleratorkey-class"></a>CMFCAcceleratorKey-Klasse
Eine Hilfsklasse, die virtuelle tastenzuordnung und Formatierung implementiert.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCAcceleratorKey : public CObject  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCAcceleratorKey::CMFCAcceleratorKey](#cmfcacceleratorkey)|Erstellt ein `CMFCAcceleratorKey`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCAcceleratorKey::Format](#format)|Übersetzt die ACCELERATION-Struktur, die die visuelle Darstellung.|  
|[CMFCAcceleratorKey::SetAccelerator](#setaccelerator)|Legt die Tastenkombination für das `CMFCAcceleratorKey` Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 Zugriffstasten werden auch bezeichnet als Tastenkombinationen. Wenn Sie möchten, um Tastenkombinationen anzuzeigen, die der Benutzer ein, die [CMFCAcceleratorKeyAssignCtrl-Klasse](../../mfc/reference/cmfcacceleratorkeyassignctrl-class.md) Maps Tastenkombinationen, z. B. Alt + Umschalt + S, um einen benutzerdefinierten Text-Format, z. B. "Alt + Umschalt + S". Jede `CMFCAcceleratorKey` Objekt ordnet eine einzelnen Tastenkombination in einem Textformat.  
  
 Weitere Informationen zur Verwendung von Tastenkombinationen und Zugriffstastentabellen finden Sie unter [CKeyboardManager Klasse](../../mfc/reference/ckeyboardmanager-class.md).  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht das Erstellen einer `CMFCAcceleratorKey` Objekt sowie zum Verwenden der `Format` Methode.  
  
 [!code-cpp[NVC_MFC_RibbonApp#30](../../mfc/reference/codesnippet/cpp/cmfcacceleratorkey-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CMFCAcceleratorKey`   
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxacceleratorkey.h  
  
##  <a name="cmfcacceleratorkey"></a>CMFCAcceleratorKey::CMFCAcceleratorKey  
 Erstellt eine [CMFCAcceleratorKey](../../mfc/reference/cmfcacceleratorkey-class.md) Objekt.  
  
```  
CMFCAcceleratorKey();  
CMFCAcceleratorKey(LPACCEL lpAccel);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpAccel`  
 Ein Zeiger auf eine Tastenkombination.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie eine Tastenkombination nicht angeben, bei der Erstellung einer `CMFCAccleratorKey`, verwenden Sie die [CMFCAcceleratorKey::SetAccelerator](#setaccelerator) Methode, um eine Tastenkombination zuzuordnen Ihrer `CMFCAcceleratorKey` Objekt.  
  
##  <a name="format"></a>CMFCAcceleratorKey::Format  
 Übersetzt die Struktur ACCELERATION seinem zugehörigen Zeichenfolgenwert an.  
  
```  
void Format(CString& str) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [out] `str`  
 Ein Verweis auf ein `CString` Objekt, in dem die Methode die übersetzte Tastenkombination schreibt.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode ruft das Zeichenfolgenformat der zugeordneten Tastenkombination ab. Sie können das Zeichenfolgenformat Festlegen einer [CMFCAcceleratorKey](../../mfc/reference/cmfcacceleratorkey-class.md) -Objekt mit dem Konstruktor oder die Methode [CMFCAcceleratorKey::SetAccelerator](#setaccelerator).  
  
##  <a name="setaccelerator"></a>CMFCAcceleratorKey::SetAccelerator  
 Legt die Tastenkombination für das [CMFCAcceleratorKey](../../mfc/reference/cmfcacceleratorkey-class.md) Objekt.  
  
```  
void SetAccelerator(LPACCEL lpAccel);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpAccel`  
 Ein Zeiger auf eine Tastenkombination.  
  
### <a name="remarks"></a>Hinweise  
 Mit dieser Methode können Sie die Tastenkombination für Festlegen einer `CMFCAcceleratorKey` Wenn Sie eine Tastenkombination nicht, beim Erstellen bereitgestellt haben der `CMFCAcceleratorKey`.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CKeyboardManager-Klasse](../../mfc/reference/ckeyboardmanager-class.md)

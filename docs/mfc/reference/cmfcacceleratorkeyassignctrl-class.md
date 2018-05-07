---
title: CMFCAcceleratorKeyAssignCtrl-Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCAcceleratorKeyAssignCtrl
- AFXACCELERATORKEYASSIGNCTRL/CMFCAcceleratorKeyAssignCtrl
- AFXACCELERATORKEYASSIGNCTRL/CMFCAcceleratorKeyAssignCtrl::CMFCAcceleratorKeyAssignCtrl
- AFXACCELERATORKEYASSIGNCTRL/CMFCAcceleratorKeyAssignCtrl::GetAccel
- AFXACCELERATORKEYASSIGNCTRL/CMFCAcceleratorKeyAssignCtrl::IsFocused
- AFXACCELERATORKEYASSIGNCTRL/CMFCAcceleratorKeyAssignCtrl::IsKeyDefined
- AFXACCELERATORKEYASSIGNCTRL/CMFCAcceleratorKeyAssignCtrl::PreTranslateMessage
- AFXACCELERATORKEYASSIGNCTRL/CMFCAcceleratorKeyAssignCtrl::ResetKey
dev_langs:
- C++
helpviewer_keywords:
- CMFCAcceleratorKeyAssignCtrl [MFC], CMFCAcceleratorKeyAssignCtrl
- CMFCAcceleratorKeyAssignCtrl [MFC], GetAccel
- CMFCAcceleratorKeyAssignCtrl [MFC], IsFocused
- CMFCAcceleratorKeyAssignCtrl [MFC], IsKeyDefined
- CMFCAcceleratorKeyAssignCtrl [MFC], PreTranslateMessage
- CMFCAcceleratorKeyAssignCtrl [MFC], ResetKey
ms.assetid: 89fb8e62-596e-4e71-8c9a-32740347aaab
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6a2906071ce1e8c8f65f21554915feed0d134276
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="cmfcacceleratorkeyassignctrl-class"></a>CMFCAcceleratorKeyAssignCtrl-Klasse
Die `CMFCAcceleratorKeyAssignCtrl` -Klasse erweitert die [CEdit-Klasse](../../mfc/reference/cedit-class.md) um zusätzliche Systemschaltflächen wie ALT, STRG und UMSCHALTTASTE zu unterstützen.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCAcceleratorKeyAssignCtrl : public CEdit  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCAcceleratorKeyAssignCtrl::CMFCAcceleratorKeyAssignCtrl](#cmfcacceleratorkeyassignctrl)|Erstellt ein `CMFCAcceleratorKeyAssignCtrl`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCAcceleratorKeyAssignCtrl::GetAccel](#getaccel)|Ruft die `ACCEL`-Struktur für eine im `CMFCAcceleratorKeyAssignCtrl`-Objekt gedrückte Tastenkombination ab.|  
|[CMFCAcceleratorKeyAssignCtrl::IsFocused](#isfocused)||  
|[CMFCAcceleratorKeyAssignCtrl::IsKeyDefined](#iskeydefined)|Bestimmt, ob eine Tastenkombination definiert wurde.|  
|[CMFCAcceleratorKeyAssignCtrl::PreTranslateMessage](#pretranslatemessage)|Wird von der [CWinApp](../../mfc/reference/cwinapp-class.md) -Klasse verwendet, um Fenstermeldungen zu übersetzen, bevor diese an die Windows-Funktionen [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) und [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) gesendet werden. (Überschreibt [CWnd::PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage).)|  
|[CMFCAcceleratorKeyAssignCtrl::ResetKey](#resetkey)|Setzt die Tastenkombination zurück.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Klasse erweitert die Funktionalität der `CEdit`-Klasse, indem Sie Unterstützung von Tastenkombinationen hinzufügt, auch bekannt als Zugriffstasten. Die `CMFCAcceleratorKeyAssignCtrl` -Klasse funktioniert als ein [CEdit-Klasse](../../mfc/reference/cedit-class.md) und Systemschaltflächen erkennen.  
  
 Diese Klasse ordnet Zeichenfolgenwerten physische Tastenkombinationen zu. Angenommen die Tastenkombination ALT+B ist der Zeichenfolge „Alt + B“ zugeordnet. Wenn der Benutzer diese Tastenkombination in einem `CMFCAcceleratorKeyAssignCtrl`-Objekt drückt, wird ihm „Alt+B“ angezeigt. Weitere Informationen zum Zuordnen von Tastenkombinationen und Zeichenfolgenformaten finden Sie unter [CMFCAcceleratorKey-Klasse](../../mfc/reference/cmfcacceleratorkey-class.md).  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht das Erstellen eines `CMFCAcceleratorKeyAssignCtrl`-Objekts und die Verwendung der `ResetKey`-Methode zum Zurücksetzen der Tastenkombination.  
  
 [!code-cpp[NVC_MFC_RibbonApp#31](../../mfc/reference/codesnippet/cpp/cmfcacceleratorkeyassignctrl-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CEdit](../../mfc/reference/cedit-class.md)  
  
 `CMFCAcceleratorKeyAssignCtrl`   
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxacceleratorkeyassignctrl.h  
  
##  <a name="cmfcacceleratorkeyassignctrl"></a>  CMFCAcceleratorKeyAssignCtrl::CMFCAcceleratorKeyAssignCtrl  
 Erstellt eine [CMFCAcceleratorKeyAssignCtrl](../../mfc/reference/cmfcacceleratorkeyassignctrl-class.md) Objekt.  
  
```  
CMFCAcceleratorKeyAssignCtrl();
```  
  
##  <a name="getaccel"></a>  CMFCAcceleratorKeyAssignCtrl::GetAccel  
 Ruft die `ACCEL` -Struktur für eine Tastenkombination gedrückt der [CMFCAcceleratorKeyAssignCtrl](../../mfc/reference/cmfcacceleratorkeyassignctrl-class.md) Objekt.  
  
```  
ACCEL const* GetAccel() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Eine `ACCEL` Struktur, die die Tastenkombination beschreibt.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Funktion zum Abrufen der `ACCEL` Struktur für eine Tastenkombination, die der Benutzer in eingegeben Ihrer `CMFCAcceleratorKeyAssignCtrl` Objekt.  
  
##  <a name="isfocused"></a>  CMFCAcceleratorKeyAssignCtrl::IsFocused  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL IsFocused() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="iskeydefined"></a>  CMFCAcceleratorKeyAssignCtrl::IsKeyDefined  
 Bestimmt, ob eine Tastenkombination in definiert wurde der [CMFCAcceleratorKeyAssignCtrl](../../mfc/reference/cmfcacceleratorkeyassignctrl-class.md) Objekt.  
  
```  
BOOL IsKeyDefined() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der Benutzer bereits eine gültige Kombination von Schlüsseln gedrückt hat, die eine Tastenkombination zu definieren; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Mit dieser Funktion können Sie bestimmen, ob der Benutzer eine gültige Tastenkombinationen in eingegeben Ihrer `CMFCAcceleratorKeyAssignCtrl` Objekt. Wenn eine Tastenkombination vorhanden ist, können Sie [CMFCAcceleratorKeyAssignCtrl::GetAccel](#getaccel) Methode zum Abrufen der `ACCEL` Struktur diese Tastenkombination zugeordnet.  
  
##  <a name="pretranslatemessage"></a>  CMFCAcceleratorKeyAssignCtrl::PreTranslateMessage  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL PreTranslateMessage(MSG* pMsg);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pMsg`  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="resetkey"></a>  CMFCAcceleratorKeyAssignCtrl::ResetKey  
 Setzt die Tastenkombination zurück.  
  
```  
void ResetKey();
```  
  
### <a name="remarks"></a>Hinweise  
 Die Funktion löscht den Edit-Steuerelement-Text. Dies schließt alle Tastenkombinationen, die der Benutzer geklickt hat.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCAcceleratorKey-Klasse](../../mfc/reference/cmfcacceleratorkey-class.md)

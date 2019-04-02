---
title: CMFCDesktopAlertWndInfo-Klasse
ms.date: 10/18/2018
f1_keywords:
- CMFCDesktopAlertWndInfo
- AFXDESKTOPALERTDIALOG/CMFCDesktopAlertWndInfo
- AFXDESKTOPALERTDIALOG/CMFCDesktopAlertWndInfo::m_hIcon
- AFXDESKTOPALERTDIALOG/CMFCDesktopAlertWndInfo::m_nURLCmdID
- AFXDESKTOPALERTDIALOG/CMFCDesktopAlertWndInfo::m_strText
- AFXDESKTOPALERTDIALOG/CMFCDesktopAlertWndInfo::m_strURL
helpviewer_keywords:
- CMFCDesktopAlertWndInfo [MFC], m_hIcon
- CMFCDesktopAlertWndInfo [MFC], m_nURLCmdID
- CMFCDesktopAlertWndInfo [MFC], m_strText
- CMFCDesktopAlertWndInfo [MFC], m_strURL
ms.assetid: 5c9bb84e-6c96-4748-8e74-6951b6ae8e84
ms.openlocfilehash: a4b3d8769b3d267c0bd3f81269dd3b8ab3cf3184
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2019
ms.locfileid: "58768288"
---
# <a name="cmfcdesktopalertwndinfo-class"></a>CMFCDesktopAlertWndInfo-Klasse

Die `CMFCDesktopAlertWndInfo` -Klasse wird zusammen mit den [CMFCDesktopAlertWnd-Klasse](../../mfc/reference/cmfcdesktopalertwnd-class.md). Bestimmt die Steuerelemente, die angezeigt werden, wenn das Desktopwarnungsfenster angezeigt wird.

## <a name="syntax"></a>Syntax

```
class CMFCDesktopAlertWndInfo
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|`CMFCDesktopAlertWndInfo::~CMFCDesktopAlertWndInfo`|Destruktor.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CMFCDesktopAlertWndInfo::operator=](#operator_eq)||

### <a name="data-members"></a>Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CMFCDesktopAlertWndInfo::m_hIcon](#m_hicon)|Ein Handle für das Symbol, das angezeigt wird.|
|[CMFCDesktopAlertWndInfo::m_nURLCmdID](#m_nurlcmdid)|Die Befehls-ID, das einen Link auf die desktop-Benachrichtigungsfenster zugeordnet ist.|
|[CMFCDesktopAlertWndInfo::m_strText](#m_strtext)|Der Text, der auf dem desktop-Benachrichtigungsfenster angezeigt wird.|
|[CMFCDesktopAlertWndInfo::m_strURL](#m_strurl)|Der Link, der auf dem desktop-Benachrichtigungsfenster angezeigt wird.|

## <a name="remarks"></a>Hinweise

Die `CMFCDesktopAlertWndInfo` Klasse wird zum Übergeben der [cmfcdesktopalertwnd:: Create](../../mfc/reference/cmfcdesktopalertwnd-class.md#create) Methode, um die Elemente anzugeben, die auf das standardmäßige Dialogfeld die desktop-Benachrichtigungsfenster angezeigt werden. Das Dialogfeld "Standard" kann es sich um drei Elemente enthalten:

- Ein Symbol, das durch den Aufruf festgelegt ist [CMFCDesktopAlertWndInfo::m_hIcon](#m_hicon).

- Eine Bezeichnung oder eine SMS, die durch den Aufruf festgelegt wird [CMFCDesktopAlertWndInfo::m_strText](#m_strtext).

- Ein Link, der durch den Aufruf festgelegt ist [CMFCDesktopAlertWndInfo::m_strURL](#m_strurl). Um den Befehl festzulegen, die ausgeführt wird, wenn auf der Link geklickt wird, rufen [CMFCDesktopAlertWndInfo::m_nURLCmdID](#m_nurlcmdid).

Wenn das Dialogfeld "Standard" nicht ausreichend ist, können Sie ein benutzerdefiniertes Dialogfeld erstellen und übergeben Sie sie an der [cmfcdesktopalertwnd:: Create](../../mfc/reference/cmfcdesktopalertwnd-class.md#create) Methode anstatt mit dieser Klasse. Weitere Informationen finden Sie unter [CMFCDesktopAlertDialog-Klasse](../../mfc/reference/cmfcdesktopalertdialog-class.md).

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird veranschaulicht, wie verschiedene Elemente in der `CMFCDesktopAlertWndInfo` Klasse. Im Beispiel wird veranschaulicht, wie das Handle auf das Symbol, das angezeigt wird, den Text festgelegt wird, der angezeigt wird, auf die desktop-Benachrichtigungsfenster, den Link, der auf dem desktop-Benachrichtigungsfenster angezeigt wird und die Befehls-ID, die einen Link auf die desktop-Benachrichtigungsfenster zugeordnet ist. In diesem Beispiel ist Teil der [Desktop Warnung Demobeispiel](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_DesktopAlertDemo#3](../../mfc/reference/codesnippet/cpp/cmfcdesktopalertwndinfo-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CMFCDesktopAlertWndInfo](../../mfc/reference/cmfcdesktopalertwndinfo-class.md)

## <a name="requirements"></a>Anforderungen

**Header:** afxDesktopAlertDialog.h

##  <a name="operator_eq"></a>  CMFCDesktopAlertWndInfo::operator =

Weitere Informationen finden Sie im Quellcode der **VC\\Atlmfc\\Src\\Mfc** Ordner von Visual Studio-Installation.

```
CMFCDesktopAlertWndInfo& operator=(CMFCDesktopAlertWndInfo& src);
```

### <a name="parameters"></a>Parameter

[in] *src*<br/>

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

##  <a name="m_hicon"></a>  CMFCDesktopAlertWndInfo::m_hIcon

Ein Handle für das Symbol, das angezeigt wird.

```
HICON m_hIcon;
```

### <a name="remarks"></a>Hinweise

##  <a name="m_nurlcmdid"></a>  CMFCDesktopAlertWndInfo::m_nURLCmdID

Die Befehls-ID, das einen Link auf die desktop-Benachrichtigungsfenster zugeordnet ist.

```
UINT m_nURLCmdID;
```

### <a name="remarks"></a>Hinweise

Die Befehls-ID wird an den Besitzer des Popup-Fenster gesendet, klickt der Benutzer auf den Link, der anhand des [CMFCDesktopAlertWndInfo::m_strURL](#m_strurl).

##  <a name="m_strtext"></a>  CMFCDesktopAlertWndInfo::m_strText

Der Text, der auf dem desktop-Benachrichtigungsfenster angezeigt wird.

```
CString m_strText;
```

### <a name="remarks"></a>Hinweise

##  <a name="m_strurl"></a>  CMFCDesktopAlertWndInfo::m_strURL

Der Link, der auf dem desktop-Benachrichtigungsfenster angezeigt wird.

```
CString m_strURL;
```

### <a name="remarks"></a>Hinweise

Der Benutzer auf den Link klickt, den Befehl, hat die [CMFCDesktopAlertWndInfo::m_nURLCmdID](#m_nurlcmdid) Befehls-ID wird an den Besitzer des Popupfensters gesendet werden.

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[Klassen](../../mfc/reference/mfc-classes.md)<br/>
[CMFCDesktopAlertWnd-Klasse](../../mfc/reference/cmfcdesktopalertwnd-class.md)<br/>
[CMFCDesktopAlertWnd::Create](../../mfc/reference/cmfcdesktopalertwnd-class.md#create)<br/>
[CMFCDesktopAlertDialog-Klasse](../../mfc/reference/cmfcdesktopalertdialog-class.md)

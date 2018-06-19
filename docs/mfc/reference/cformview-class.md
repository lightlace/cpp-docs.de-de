---
title: CFormView-Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CFormView
- AFXEXT/CFormView
- AFXEXT/CFormView::CFormView
- AFXEXT/CFormView::IsInitDlgCompleted
dev_langs:
- C++
helpviewer_keywords:
- CFormView [MFC], CFormView
- CFormView [MFC], IsInitDlgCompleted
ms.assetid: a99ec313-36f0-4f28-9d2b-de11de14ac19
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3486285b7b6430e9cd6f0e4a936aa3341bd72e0f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33366579"
---
# <a name="cformview-class"></a>CFormView-Klasse
Die für Formularansichten verwendete Basisklasse.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CFormView : public CScrollView  
```  
  
## <a name="members"></a>Member  
  
### <a name="protected-constructors"></a>Geschützte Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CFormView::CFormView](#cformview)|Erstellt ein `CFormView`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CFormView::IsInitDlgCompleted](#isinitdlgcompleted)|Wird für die Synchronisierung während der Initialisierung verwendet.|  
  
## <a name="remarks"></a>Hinweise  
 Eine Formularansicht ist im Wesentlichen eine Ansicht, die Steuerelemente enthält. Diese Steuerelemente werden basierend auf einer Dialogfeldvorlagenressource angeordnet. Verwenden Sie `CFormView`, wenn Sie Formulare in der Anwendung verwenden möchten. Diese Ansichten unterstützen bei Bedarf mithilfe der [CScrollView](../../mfc/reference/cscrollview-class.md) Funktionalität.  
  
 Wenn Sie sind [Erstellen einer formularbasierten Anwendung](../../mfc/reference/creating-a-forms-based-mfc-application.md), Sie können ihre Ansichtsklasse auf `CFormView`, somit zu einer formularbasierten Anwendung.  
  
 Sie können auch neue einfügen [Formularthemen](../../mfc/form-views-mfc.md) in Dokument-Ansicht-basierten Anwendungen. Auch wenn die Anwendung ursprünglich keine Formulare unterstützte, fügt Visual C++ diese Unterstützung hinzu, wenn Sie ein neues Formular einfügen.  
  
 Der MFC-Anwendungs-Assistent und der Befehl "Klasse hinzufügen" sind die bevorzugten Methoden zum Erstellen formularbasierter Anwendungen. Wenn Sie zum Erstellen einer formularbasierten Anwendung benötigen ohne die Verwendung dieser Methoden finden Sie unter [Erstellen einer formularbasierten Anwendung](../../mfc/reference/creating-a-forms-based-mfc-application.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CView](../../mfc/reference/cview-class.md)  
  
 [CScrollView](../../mfc/reference/cscrollview-class.md)  
  
 `CFormView`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxext.h  
  
##  <a name="cformview"></a>  CFormView::CFormView  
 Erstellt ein `CFormView`-Objekt.  
  
```  
CFormView(LPCTSTR lpszTemplateName);  
CFormView(UINT nIDTemplate);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszTemplateName`  
 Enthält eine Null-terminierte Zeichenfolge, die den Namen einer Dialogfeldvorlagen-Ressource ist.  
  
 `nIDTemplate`  
 Enthält die ID-Nummer einer Dialogfeldvorlagen-Ressource.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie ein Objekt eines Typs erstellen von abgeleiteten `CFormView`, Aufrufen eines Konstruktors erstellen das Ansichtsobjekt und identifizieren die Dialogressource, auf denen die Sicht basiert. Sie können die Ressource anhand des Namens (übergeben Sie eine Zeichenfolge als Argument an den Konstruktor) oder nach seiner ID (übergeben Sie eine Ganzzahl ohne Vorzeichen als Argument) identifizieren.  
  
 Die Formularansicht Fenster und untergeordnete Steuerelemente werden erst erstellt, wenn `CWnd::Create` aufgerufen wird. `CWnd::Create` wird vom Framework als Teil des Erstellungsprozesses Dokument und Ansicht aufgerufen, die durch die Dokumentvorlage gesteuert wird.  
  
> [!NOTE]
>  Die abgeleitete Klasse *müssen* Geben Sie einen eigenen Konstruktor. In den Konstruktor aufrufen des Konstruktors und `CFormView::CFormView`, mit dem Ressourcennamen oder -ID als ein Argument an, wie in der vorherigen Klassenübersicht dargestellt.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView#90](../../mfc/codesnippet/cpp/cformview-class_1.h)]  
  
 [!code-cpp[NVC_MFCDocView#91](../../mfc/codesnippet/cpp/cformview-class_2.cpp)]  
  
##  <a name="isinitdlgcompleted"></a>  CFormView::IsInitDlgCompleted  
 Von MFC verwendet, um sicherzustellen, dass die Initialisierung abgeschlossen ist, bevor andere Vorgänge ausgeführt werden.  
  
```  
BOOL IsInitDlgCompleted() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 TRUE, wenn die Initialisierungsfunktion für diesen Dialog abgeschlossen wurde.  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel SNAPVW](../../visual-cpp-samples.md)   
 [MFC-Beispiel VIEWEX](../../visual-cpp-samples.md)   
 [CScrollView-Klasse](../../mfc/reference/cscrollview-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CDialog-Klasse](../../mfc/reference/cdialog-class.md)   
 [CScrollView-Klasse](../../mfc/reference/cscrollview-class.md)

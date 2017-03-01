---
title: CFormView Class | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CFormView
dev_langs:
- C++
helpviewer_keywords:
- views, containing controls
- CFormView class
- form views
ms.assetid: a99ec313-36f0-4f28-9d2b-de11de14ac19
caps.latest.revision: 23
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
ms.openlocfilehash: 82b38b04aa3cf2368d41ee20847c952c3082d4e4
ms.lasthandoff: 02/24/2017

---
# <a name="cformview-class"></a>CFormView-Klasse
Die für Formularansichten verwendete Basisklasse.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CFormView : public CScrollView  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="protected-constructors"></a>Geschützte Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CFormView::CFormView](#cformview)|Erstellt ein `CFormView`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CFormView::IsInitDlgCompleted](#isinitdlgcompleted)|Wird für die Synchronisierung während der Initialisierung verwendet.|  
  
## <a name="remarks"></a>Hinweise  
 Eine Formularansicht ist im Wesentlichen eine Ansicht, die Steuerelemente enthält. Diese Steuerelemente werden basierend auf einer Dialogfeldvorlagenressource angeordnet. Verwenden Sie `CFormView`, wenn Sie Formulare in der Anwendung verwenden möchten. Diese Ansichten zu unterstützen, Bildlauf bei Bedarf mithilfe der [CScrollView](../../mfc/reference/cscrollview-class.md) Funktionalität.  
  
 Wenn [Erstellen einer formularbasierten Anwendung](../../mfc/reference/creating-a-forms-based-mfc-application.md), seine Ansichtsklasse auf Grundlage `CFormView`, wodurch eine formularbasierte Anwendung.  
  
 Sie können auch neue einfügen [Themen zu Formularen](../../mfc/form-views-mfc.md) in Dokument-View-basierte Clientanwendungen. Auch wenn die Anwendung ursprünglich keine Formulare unterstützte, fügt Visual C++ diese Unterstützung hinzu, wenn Sie ein neues Formular einfügen.  
  
 Der MFC-Anwendungs-Assistent und der Befehl "Klasse hinzufügen" sind die bevorzugten Methoden zum Erstellen formularbasierter Anwendungen. Wenn Sie müssen zum Erstellen einer formularbasierten Anwendung ohne Verwendung dieser Methoden finden Sie unter [Erstellen einer formularbasierten Anwendung](../../mfc/reference/creating-a-forms-based-mfc-application.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CView](../../mfc/reference/cview-class.md)  
  
 [CScrollView](../../mfc/reference/cscrollview-class.md)  
  
 `CFormView`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxext.h  
  
##  <a name="a-namecformviewa--cformviewcformview"></a><a name="cformview"></a>CFormView::CFormView  
 Erstellt ein `CFormView`-Objekt.  
  
```  
CFormView(LPCTSTR lpszTemplateName);  
CFormView(UINT nIDTemplate);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszTemplateName`  
 Enthält eine auf Null endende Zeichenfolge, die den Namen einer Dialogfeldvorlagen-Ressource ist.  
  
 `nIDTemplate`  
 Enthält die ID-Nummer einer Dialogfeldvorlagen-Ressource.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie ein Objekt eines Typs erstellen von abgeleiteten `CFormView`, rufen Sie die Konstruktoren das View-Objekt erstellen und identifizieren die Dialogfeldressource, auf denen die Sicht basiert. Sie können die Ressource anhand des Namens (übergeben Sie eine Zeichenfolge als Argument an den Konstruktor) oder nach seiner ID (übergeben Sie eine ganze Zahl als Argument) identifizieren.  
  
 Die Formularansicht Fenster und die untergeordneten Steuerelemente werden nicht erstellt, bis `CWnd::Create` aufgerufen wird. `CWnd::Create`wird vom Framework als Teil des Erstellungsprozesses Dokument und Ansicht aufgerufen, die durch die Dokumentvorlage gesteuert wird.  
  
> [!NOTE]
>  Die abgeleitete Klasse *müssen* Geben Sie einen eigenen Konstruktor. Rufen Sie im Konstruktor den Konstruktor `CFormView::CFormView`, mit dem Ressourcennamen oder die ID als ein Argument an, wie in der vorherigen Klassenübersicht dargestellt.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView&#90;](../../mfc/codesnippet/cpp/cformview-class_1.h)]  
  
 [!code-cpp[NVC_MFCDocView&#91;](../../mfc/codesnippet/cpp/cformview-class_2.cpp)]  
  
##  <a name="a-nameisinitdlgcompleteda--cformviewisinitdlgcompleted"></a><a name="isinitdlgcompleted"></a>CFormView::IsInitDlgCompleted  
 Von MFC verwendet, um sicherzustellen, dass die Initialisierung abgeschlossen ist, bevor andere Vorgänge ausgeführt werden.  
  
```  
BOOL IsInitDlgCompleted() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 TRUE, wenn die Initialisierungsfunktion für diesen Dialog abgeschlossen wurde.  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel SNAPVW](../../visual-cpp-samples.md)   
 [MFC-Beispiel Wahl](../../visual-cpp-samples.md)   
 [CScrollView-Klasse](../../mfc/reference/cscrollview-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CDialog-Klasse](../../mfc/reference/cdialog-class.md)   
 [CScrollView-Klasse](../../mfc/reference/cscrollview-class.md)


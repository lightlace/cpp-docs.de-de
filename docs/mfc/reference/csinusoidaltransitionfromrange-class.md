---
title: CSinusoidalTransitionFromRange-Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CSinusoidalTransitionFromRange
- AFXANIMATIONCONTROLLER/CSinusoidalTransitionFromRange
- AFXANIMATIONCONTROLLER/CSinusoidalTransitionFromRange::CSinusoidalTransitionFromRange
- AFXANIMATIONCONTROLLER/CSinusoidalTransitionFromRange::Create
- AFXANIMATIONCONTROLLER/CSinusoidalTransitionFromRange::m_dblMaximumValue
- AFXANIMATIONCONTROLLER/CSinusoidalTransitionFromRange::m_dblMinimumValue
- AFXANIMATIONCONTROLLER/CSinusoidalTransitionFromRange::m_duration
- AFXANIMATIONCONTROLLER/CSinusoidalTransitionFromRange::m_period
- AFXANIMATIONCONTROLLER/CSinusoidalTransitionFromRange::m_slope
dev_langs:
- C++
helpviewer_keywords:
- CSinusoidalTransitionFromRange [MFC], CSinusoidalTransitionFromRange
- CSinusoidalTransitionFromRange [MFC], Create
- CSinusoidalTransitionFromRange [MFC], m_dblMaximumValue
- CSinusoidalTransitionFromRange [MFC], m_dblMinimumValue
- CSinusoidalTransitionFromRange [MFC], m_duration
- CSinusoidalTransitionFromRange [MFC], m_period
- CSinusoidalTransitionFromRange [MFC], m_slope
ms.assetid: 8b66a729-5f10-431a-b055-e3600d0065da
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 646878a1cfd77dd61fbb854512c56512083ff609
ms.sourcegitcommit: be0e3457f2884551f18e183ef0ea65c3ded7f689
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/28/2018
ms.locfileid: "37078682"
---
# <a name="csinusoidaltransitionfromrange-class"></a>CSinusoidalTransitionFromRange-Klasse
Kapselt einen Übergang mit sinusförmigem Bereich und angegebenem Schwingungsbereich.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CSinusoidalTransitionFromRange : public CBaseTransition;  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CSinusoidalTransitionFromRange::CSinusoidalTransitionFromRange](#csinusoidaltransitionfromrange)|Erstellt ein Übergangsobjekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CSinusoidalTransitionFromRange::Create](#create)|Ruft den Übergangsbibliothek, um die gekapselte COM-Übergangsobjekt zu erstellen. (Überschreibt [CBaseTransition:: Create](../../mfc/reference/cbasetransition-class.md#create).)|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CSinusoidalTransitionFromRange::m_dblMaximumValue](#m_dblmaximumvalue)|Der Wert der Animationsvariablen an eine Spitze des mit sinusförmiger Wave.|  
|[CSinusoidalTransitionFromRange::m_dblMinimumValue](#m_dblminimumvalue)|Der Wert der Animationsvariablen bei einem Tiefpunkt mit sinusförmiger Welle.|  
|[CSinusoidalTransitionFromRange::m_duration](#m_duration)|Die Dauer des Übergangs.|  
|[CSinusoidalTransitionFromRange::m_period](#m_period)|Der Zeitraum und angegebenem schwingungsbereich mit sinusförmiger Welle in Sekunden.|  
|[CSinusoidalTransitionFromRange::m_slope](#m_slope)|Die Kurve am Anfang des Übergangs.|  
  
## <a name="remarks"></a>Hinweise  
 Der Wert der Animationsvariablen wechselt zwischen den angegebenen minimalen und maximalen Werten über die gesamte Dauer eines Übergangs mit sinusförmigem. Die Steigung-Parameter wird verwendet, um zwischen zwei möglichen Sinus Wellen von den anderen Parametern angegeben zu unterscheiden. Da alle Übergänge automatisch gelöscht werden, es wird empfohlen, belegt sie mit dem Operator new. Das gekapselte IUIAnimationTransition-COM-Objekt wird von CAnimationController:: erst erstellt, ist es auf NULL. Ändern Membervariablen, nach der Erstellung dieses COM-Objekt hat keine Auswirkung.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CBaseTransition](../../mfc/reference/cbasetransition-class.md)  
  
 [CSinusoidalTransitionFromRange](../../mfc/reference/csinusoidaltransitionfromrange-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxanimationcontroller.h  
  
##  <a name="create"></a>  CSinusoidalTransitionFromRange::Create  
 Ruft den Übergangsbibliothek, um die gekapselte COM-Übergangsobjekt zu erstellen.  
  
```  
virtual BOOL Create(
    IUIAnimationTransitionLibrary* pLibrary,  
    IUIAnimationTransitionFactory* \*not used*\);
```  
  
### <a name="parameters"></a>Parameter  
 *pLibrary*  
 Ein Zeiger auf den Übergangsbibliothek, die für die Erstellung der standardmäßigen Übergänge verwendet wird.  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn der Übergang erfolgreich erstellt wurde. andernfalls "false".  
  
##  <a name="csinusoidaltransitionfromrange"></a>  CSinusoidalTransitionFromRange::CSinusoidalTransitionFromRange  
 Erstellt ein Übergangsobjekt.  
  
```  
CSinusoidalTransitionFromRange(
    UI_ANIMATION_SECONDS duration,  
    DOUBLE dblMinimumValue,  
    DOUBLE dblMaximumValue,  
    UI_ANIMATION_SECONDS period,  
    UI_ANIMATION_SLOPE slope);
```  
  
### <a name="parameters"></a>Parameter  
 *Dauer*  
 Die Dauer des Übergangs.  
  
 *dblMinimumValue*  
 Der Wert der Animationsvariablen bei einem Tiefpunkt mit sinusförmiger Welle.  
  
 *dblMaximumValue*  
 Der Wert der Animationsvariablen an eine Spitze des mit sinusförmiger Wave.  
  
 *Zeitraum*  
 Der Zeitraum und angegebenem schwingungsbereich mit sinusförmiger Welle in Sekunden.  
  
 *Steigung*  
 Die Kurve am Anfang des Übergangs.  
  
##  <a name="m_dblmaximumvalue"></a>  CSinusoidalTransitionFromRange::m_dblMaximumValue  
 Der Wert der Animationsvariablen an eine Spitze des mit sinusförmiger Wave.  
  
```  
DOUBLE m_dblMaximumValue;  
```  
  
##  <a name="m_dblminimumvalue"></a>  CSinusoidalTransitionFromRange::m_dblMinimumValue  
 Der Wert der Animationsvariablen bei einem Tiefpunkt mit sinusförmiger Welle.  
  
```  
DOUBLE m_dblMinimumValue;  
```  
  
##  <a name="m_duration"></a>  CSinusoidalTransitionFromRange::m_duration  
 Die Dauer des Übergangs.  
  
```  
UI_ANIMATION_SECONDS m_duration;  
```  
  
##  <a name="m_period"></a>  CSinusoidalTransitionFromRange::m_period  
 Der Zeitraum und angegebenem schwingungsbereich mit sinusförmiger Welle in Sekunden.  
  
```  
UI_ANIMATION_SECONDS m_period;  
```  
  
##  <a name="m_slope"></a>  CSinusoidalTransitionFromRange::m_slope  
 Die Kurve am Anfang des Übergangs.  
  
```  
UI_ANIMATION_SLOPE m_slope;  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Klassen](../../mfc/reference/mfc-classes.md)

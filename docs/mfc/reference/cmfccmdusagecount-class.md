---
title: CMFCCmdUsageCount-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCCmdUsageCount
- AFXCMDUSAGECOUNT/CMFCCmdUsageCount
- AFXCMDUSAGECOUNT/CMFCCmdUsageCount::AddCmd
- AFXCMDUSAGECOUNT/CMFCCmdUsageCount::GetCount
- AFXCMDUSAGECOUNT/CMFCCmdUsageCount::HasEnoughInformation
- AFXCMDUSAGECOUNT/CMFCCmdUsageCount::IsFreqeuntlyUsedCmd
- AFXCMDUSAGECOUNT/CMFCCmdUsageCount::Reset
- AFXCMDUSAGECOUNT/CMFCCmdUsageCount::Serialize
- AFXCMDUSAGECOUNT/CMFCCmdUsageCount::SetOptions
dev_langs:
- C++
helpviewer_keywords:
- CMFCCmdUsageCount [MFC], AddCmd
- CMFCCmdUsageCount [MFC], GetCount
- CMFCCmdUsageCount [MFC], HasEnoughInformation
- CMFCCmdUsageCount [MFC], IsFreqeuntlyUsedCmd
- CMFCCmdUsageCount [MFC], Reset
- CMFCCmdUsageCount [MFC], Serialize
- CMFCCmdUsageCount [MFC], SetOptions
ms.assetid: 9c33b783-37c0-43ea-9f31-3c75e246c841
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a1e28b9c28823e77244bc6e686db163e5110a8fa
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45719965"
---
# <a name="cmfccmdusagecount-class"></a>CMFCCmdUsageCount-Klasse
Überwacht die Verwendungsanzahl der Windows-Meldungen, z. B. wenn der Benutzer ein Element in einem Menü auswählt.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCCmdUsageCount : public CObject  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|||  
|-|-|  
|Name|Beschreibung|  
|`CMFCCmdUsageCount::CMFCCmdUsageCount`|Standardkonstruktor|  
|`CMFCCmdUsageCount::~CMFCCmdUsageCount`|Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|||  
|-|-|  
|Name|Beschreibung|  
|[CMFCCmdUsageCount::AddCmd](#addcmd)|Inkrementiert durch eine der Zähler, der den angegebenen Befehl zugeordnet ist.|  
|[CMFCCmdUsageCount::GetCount](#getcount)|Ruft die Anzahl der Nutzung, die der angegebenen Befehls-ID zugeordnet ist|  
|[CMFCCmdUsageCount::HasEnoughInformation](#hasenoughinformation)|Bestimmt, ob dieses Objekt die Mindestmenge an Überwachungsdaten gesammelt wurden.|  
|[:: Isfreqeuntlyusedcmd](#isfreqeuntlyusedcmd)|Bestimmt, ob der angegebene Befehl häufig verwendet wird.|  
|[CMFCCmdUsageCount::Reset](#reset)|Löscht die Verwendungsanzahl der aller Befehle.|  
|[CMFCCmdUsageCount::Serialize](#serialize)|Dieses Objekt aus einem Archiv liest oder schreibt dieses in ein Archiv. (Überschreibt [CObject::Serialize](../../mfc/reference/cobject-class.md#serialize).)|  
|[CMFCCmdUsageCount::SetOptions](#setoptions)|Legt die Werte der freigegebenen `CMFCCmdUsageCount` Klassendatenmember.|  
  
### <a name="data-members"></a>Datenmember  
  
|||  
|-|-|  
|name|Beschreibung|  
|`m_CmdUsage`|Ein `CMap` -Objekt, das Befehle ihre Verwendungszähler zugeordnet ist.|  
|`m_nMinUsagePercentage`|Die minimale Auslastung in Prozent für einen Befehl, häufig verwendet werden soll.|  
|`m_nStartCount`|Der Start-Zähler, der verwendet wird, um festzustellen, ob dieses Objekt die Mindestmenge an Überwachungsdaten gesammelt wurden.|  
|`m_nTotalUsage`|Die Anzahl von alle nachverfolgten Befehle.|  
  
### <a name="remarks"></a>Hinweise  
 Die `CMFCCmdUsageCount` -Klasse ordnet jedes numerischen Bezeichner des Windows-Meldung zu einem Zähler für die 32-Bit-Ganzzahl ohne Vorzeichen. `CMFCToolBar` Mithilfe dieser Klasse häufig verwendete Symbolleistenelemente angezeigt. Weitere Informationen zu `CMFCToolBar`, finden Sie unter [CMFCToolBar-Klasse](../../mfc/reference/cmfctoolbar-class.md).  
  
 Sie können beibehalten `CMFCCmdUsageCount` -Klasse Daten zwischen den Ausführungen des Programms. Verwenden der [CMFCCmdUsageCount::Serialize](#serialize) -Methode zum Serialisieren von Daten und die [CMFCCmdUsageCount::SetOptions](#setoptions) Methode, um freigegebene Daten festzulegen.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCCmdUsageCount](../../mfc/reference/cmfccmdusagecount-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxcmdusagecount.h  
  
##  <a name="addcmd"></a>  CMFCCmdUsageCount::AddCmd  
 Inkrementiert durch eine der Zähler, der den angegebenen Befehl zugeordnet ist.  
  
```  
void AddCmd(UINT uiCmd);
```  
  
### <a name="parameters"></a>Parameter  
  
|||  
|-|-|  
|Parameter|Beschreibung|  
|*uiCmd*|[in] Gibt an, der Befehl Zähler erhöht.|  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode fügt einen neuen Eintrag der Map-Struktur des Befehls Anzahl, `m_CmdUsage`, wenn der Eintrag nicht bereits vorhanden ist.  
  
 Diese Methode ist "nothing" in den folgenden Fällen:  
  
-   Das Framework für die Symbolleiste befindet sich in den Anpassungsmodus (die [CMFCToolBar::IsCustomizeMode](../../mfc/reference/cmfctoolbar-class.md#iscustomizemode) Methode gibt einen Wert ungleich NULL zurück).  
  
-   Der Befehl bezieht sich auf die ein Trennzeichen Untermenü oder Menü ( *UiCmd* gleich 0 oder 1).  
  
- *UiCmd* bezieht sich auf einen standard-Befehl (die globale `IsStandardCommand` Funktion gibt einen Wert ungleich NULL zurück).  
  
##  <a name="getcount"></a>  CMFCCmdUsageCount::GetCount  
 Ruft die Anzahl der Nutzung, die der angegebenen Befehls-ID zugeordnet ist  
  
```  
UINT GetCount(UINT uiCmd) const;  
```  
  
### <a name="parameters"></a>Parameter  
  
|||  
|-|-|  
|Parameter|Beschreibung|  
|*uiCmd*|[in] Die ID des Leistungsindikators "Befehl" abgerufen werden soll.|  
  
### <a name="return-value"></a>Rückgabewert  
 Die Verwendungsanzahl der, die der angegebenen Befehls-ID zugeordnet ist.  
  
##  <a name="hasenoughinformation"></a>  CMFCCmdUsageCount::HasEnoughInformation  
 Bestimmt, ob dieses Objekt die Mindestmenge an Überwachungsdaten erhalten hat.  
  
```  
BOOL HasEnoughInformation() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn dieses Objekt verfügt über die Mindestmenge an Überwachungsdaten empfangen. andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode gibt einen Wert ungleich NULL zurück, wenn die Gesamtanzahl, `m_nTotalUsage`, alle nachverfolgten Befehle ist gleich oder größer als die anfängliche Anzahl `m_nStartCount`. Standardmäßig legt das Framework die anfängliche Anzahl 0 fest. Sie können diesen Wert überschreiben, indem die [CMFCCmdUsageCount::SetOptions](#setoptions) Methode.  
  
 Diese Methode wird verwendet, indem [CMFCMenuBar::IsShowAllCommands](../../mfc/reference/cmfcmenubar-class.md#isshowallcommands) zu bestimmen, ob alle im Kontextmenü verfügbaren Befehle angezeigt.  
  
##  <a name="isfreqeuntlyusedcmd"></a>  :: Isfreqeuntlyusedcmd  
 Bestimmt, ob der angegebene Befehl häufig verwendet wird.  
  
```  
BOOL IsFreqeuntlyUsedCmd(UINT uiCmd) const;  
```  
  
### <a name="parameters"></a>Parameter  
  
|||  
|-|-|  
|Parameter|Beschreibung|  
|*uiCmd*|[in] Gibt den Befehl aus, um zu überprüfen.|  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn der Befehl häufig verwendet wird; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode gibt 0 zurück, wenn die gesamte Befehlssyntax `m_nTotalUsage`, ist 0. Diese Methode zurückgibt, andernfalls ungleich NULL, wenn der Prozentsatz, der der angegebene Befehl dient, den minimalen Prozentsatz, übersteigt `m_nMinUsagePercentage`. Standardmäßig legt das Framework den minimalen Prozentsatz auf 5 fest. Sie können diesen Wert überschreiben, indem die [CMFCCmdUsageCount::SetOptions](#setoptions) Methode. Wenn Sie der minimale Prozentsatz 0 ist, gibt diese Methode ungleich NULL, wenn die Anzahl der angegebenen Befehls größer als 0 ist.  
  
 [CMFCToolBar::IsCommandRarelyUsed](../../mfc/reference/cmfctoolbar-class.md#iscommandrarelyused) verwendet diese Methode, um zu bestimmen, ob ein Befehl nur selten verwendet wird.  
  
##  <a name="reset"></a>  CMFCCmdUsageCount::Reset  
 Löscht die Verwendungsanzahl der aller Befehle.  
  
```  
void Reset();
```  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode zum Löschen der alle Einträge aus der Struktur der Zuordnung der Befehl Anzahl der `m_CmdUsage`, und die Nutzung insgesamt Befehl Zurücksetzen `m_nTotalUsage`, Leistungsindikator auf 0.  
  
##  <a name="serialize"></a>  CMFCCmdUsageCount::Serialize  
 Dieses Objekt aus einem Archiv liest oder schreibt dieses in ein Archiv.  
  
```  
virtual void Serialize(CArchive& ar);
```  
  
### <a name="parameters"></a>Parameter  
  
|||  
|-|-|  
|Parameter|Beschreibung|  
|*ar*|[in] Ein `CArchive` zu von oder zu serialisierende Objekt.|  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode serialisiert die Map-Struktur, der Anzahl der Befehl, `m_CmdUsage`, und die Nutzung insgesamt Befehl `m_nTotalUsage`, Leistungsindikator aus oder in die angegebene Archivdatei.  
  
 Beispiele zur Serialisierung finden Sie [Serialisierung: Serialisieren eines Objekts](../../mfc/serialization-serializing-an-object.md).  
  
##  <a name="setoptions"></a>  CMFCCmdUsageCount::SetOptions  
 Legt die Werte der freigegebenen `CMFCCmdUsageCount` Klassendatenmember.  
  
```  
static BOOL __stdcall SetOptions(
    UINT nStartCount,  
    UINT nMinUsagePercentage);
```  
  
### <a name="parameters"></a>Parameter  
  
|||  
|-|-|  
|Parameter|Beschreibung|  
|*nStartCount*|[in] Die neue anfängliche Anzahl von alle nachverfolgten Befehlen.|  
|*nMinUsagePercentage*|[in] Der neue minimale Auslastung in Prozent.|  
  
### <a name="return-value"></a>Rückgabewert  
 TRUE, wenn die Methode erfolgreich ist, FALSE, wenn die *nMinUsagePercentage* -Parameter ist größer als oder gleich 100.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird die freigegebene `CMFCCmdUsageCount` Klassendatenmember `m_nStartCount` und `m_nMinUsagePercentage` zu *nStartCount* und *nMinUsagePercentage*bzw. `m_nStartCount` wird verwendet, durch die [CMFCCmdUsageCount::HasEnoughInformation](#hasenoughinformation) Methode, um zu bestimmen, ob dieses Objekt die Mindestmenge an Überwachungsdaten gesammelt wurden. `m_nMinUsagePercentage` wird verwendet, durch die [:: Isfreqeuntlyusedcmd](#isfreqeuntlyusedcmd) Methode, um zu bestimmen, ob ein bestimmter Befehl häufig verwendet wird.  
  
 In Debugbuilds diese Methode generiert ein Assertionsfehler ausgelöst, wenn die *nMinUsagePercentage* -Parameter ist größer als oder gleich 100.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCToolBar-Klasse](../../mfc/reference/cmfctoolbar-class.md)

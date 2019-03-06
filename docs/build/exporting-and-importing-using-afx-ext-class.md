---
title: Exportieren und Importieren mithilfe von AFX_EXT_CLASS
ms.date: 11/04/2016
f1_keywords:
- afx_ext_class
helpviewer_keywords:
- AFX_EXT_CLASS macro
- exporting classes [C++]
- importing DLLs [C++]
- extension DLLs [C++], exporting classes
- executable files [C++], importing classes
- exporting DLLs [C++], AFX_EXT_CLASS macro
ms.assetid: 6b72cb2b-e92e-4ecd-bcab-c335e1d1cfde
ms.openlocfilehash: 1451b452c5e2dc62e83e5b8f473248fa7c231877
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57421193"
---
# <a name="exporting-and-importing-using-afxextclass"></a>Exportieren und Importieren mithilfe von AFX_EXT_CLASS

[MFC-Erweiterungs-DLLs](../build/extension-dlls-overview.md) verwenden Sie das Makro **AFX_EXT_CLASS** zum Exportieren von Klassen, die ausführbaren Dateien, die mit der MFC-Erweiterungs-DLL verknüpft wird das Makro verwenden, um Klassen zu importieren. Mit der **AFX_EXT_CLASS** Makro, das die gleichen Headerdateien, die verwendet werden, erstellen Sie die MFC-Erweiterungs-DLL mit der ausführbaren Dateien, die mit der DLL verwendet werden kann.

Fügen Sie in der Headerdatei für die DLL der **AFX_EXT_CLASS** Schlüsselwort, um die Deklaration der Klasse wie folgt:

```cpp
class AFX_EXT_CLASS CMyClass : public CDocument
{
// <body of class>
};
```

Dieses Makro wird definiert, von MFC als `__declspec(dllexport)` bei der die Präprozessorsymbole `_AFXDLL` und `_AFXEXT` definiert sind. Aber das Makro wird definiert als `__declspec(dllimport)` beim `_AFXDLL` definiert ist und `_AFXEXT` ist nicht definiert. Wenn definiert, das Präprozessorsymbol `_AFXDLL` gibt an, dass die freigegebene Version von MFC von der ausführbaren Zieldatei (eine DLL oder einer Anwendung) verwendet wird. Wenn beide `_AFXDLL` und `_AFXEXT` werden definiert, das bedeutet, dass die ausführbare Zieldatei eine MFC-Erweiterungs-DLL ist.

Da `AFX_EXT_CLASS` ist definiert als `__declspec(dllexport)` Wenn aus einer MFC-Erweiterungs-DLL zu exportieren, können Sie ganze Klassen exportieren, ohne dass die ergänzten Namen für alle von dieser Klasse Symbolen in der DEF-Datei.

Auch wenn Sie eine DEF-Datei und aller die ergänzten Namen für die Klasse erstellen, mit dieser Methode vermeiden können, ist eine DEF-Datei erstellen effizienter, da die Namen anhand der Ordinalzahl exportiert werden können. Um die DEF-Datei-Methode für das Exportieren zu verwenden, platzieren Sie den folgenden Code am Anfang und Ende der Headerdatei ein:

```cpp
#undef AFX_DATA
#define AFX_DATA AFX_EXT_DATA
// <body of your header file>
#undef AFX_DATA
#define AFX_DATA
```

> [!CAUTION]
>  Achten Sie darauf beim Exportieren von Inlinefunktionen, da sie die Möglichkeit, Konflikte zwischen Versionen erstellt werden können. Eine Inlinefunktion Ruft im Anwendungscode erweitert. aus diesem Grund, wenn Sie später die Funktion umschreiben, wird es nicht aktualisiert, wenn die Anwendung selbst neu kompiliert wird. DLL-Funktionen können in der Regel aktualisiert werden, ohne Neuerstellung von Anwendungen, die sie verwenden.

## <a name="exporting-individual-members-in-a-class"></a>Exportieren die einzelnen Elemente in einer Klasse

In einigen Fällen empfiehlt es sich um einzelne Member der Klasse zu exportieren. Angenommen, Sie exportieren eine `CDialog`-abgeleitete Klasse sein, benötigen Sie möglicherweise nur um den Konstruktor zu exportieren und die `DoModal` aufrufen. Sie können `AFX_EXT_CLASS` auf die einzelnen Mitglieder, die Sie exportieren möchten.

Zum Beispiel:

```cpp
class CExampleDialog : public CDialog
{
public:
   AFX_EXT_CLASS CExampleDialog();
   AFX_EXT_CLASS int DoModal();
   ...
   // rest of class definition
   ...
};
```

Da Sie nicht mehr alle Member der Klasse exportieren, können Sie ein zusätzliches Problem aufgrund der Art und Weise die MFC-Makros Arbeit ausführen. Einige der MFC Hilfsmakros tatsächlich deklarieren oder definieren Datenelemente. Daher müssen diese Datenelemente auch aus einer DLL exportiert werden.

Z. B. die `DECLARE_DYNAMIC` Makro wird wie folgt definiert, wenn Sie eine MFC-Erweiterungs-DLL zu erstellen:

```cpp
#define DECLARE_DYNAMIC(class_name) \
protected: \
   static CRuntimeClass* PASCAL _GetBaseClass(); \
public: \
   static AFX_DATA CRuntimeClass class##class_name; \
   virtual CRuntimeClass* GetRuntimeClass() const; \
```

Die Zeile, die mit statischen beginnt `AFX_DATA` ein statisches Objekt innerhalb der Klasse deklariert. Um diese Klasse ordnungsgemäß zu exportieren und auf die Laufzeit-Informationen aus einem ausführbaren Client zugreifen, müssen Sie diese statische Objekt exportieren. Da die statische Objekt mit dem Modifizierer deklariert wird `AFX_DATA`, müssen Sie nur definieren `AFX_DATA` sein `__declspec(dllexport)` beim Erstellen der DLL und definieren ihn als `__declspec(dllimport)` beim Erstellen der ausführbare Client. Da `AFX_EXT_CLASS` ist bereits definiert. auf diese Weise müssen Sie nur redefine `AFX_DATA` identisch sein `AFX_EXT_CLASS` Ihrer Klassendefinition.

Zum Beispiel:

```cpp
#undef  AFX_DATA
#define AFX_DATA AFX_EXT_CLASS

class CExampleView : public CView
{
   DECLARE_DYNAMIC()
   // ... class definition ...
};

#undef  AFX_DATA
#define AFX_DATA
```

MFC verwendet stets die `AFX_DATA` Symbol für Datenelemente, die sie innerhalb der Makros definiert diese Technik funktioniert für alle derartigen Szenarien. Angenommen, dies funktioniert für `DECLARE_MESSAGE_MAP`.

> [!NOTE]
>  Wenn Sie anstelle von ausgewählten Member der Klasse die gesamte Klasse exportieren, werden automatisch statischen Datenmember exportiert.

### <a name="what-do-you-want-to-do"></a>Wie möchten Sie vorgehen?

- [Exportieren Sie aus einer DLL mithilfe von DEF-Dateien](../build/exporting-from-a-dll-using-def-files.md)

- [Exportieren Sie aus einer DLL mithilfe von __declspec(dllexport)](../build/exporting-from-a-dll-using-declspec-dllexport.md)

- [Exportieren von C++-Funktionen für die Verwendung in ausführbaren c-Dateien](../build/exporting-cpp-functions-for-use-in-c-language-executables.md)

- [Exportieren von C-Funktionen für die Verwendung in ausführbaren C oder C++-Dateien](../build/exporting-c-functions-for-use-in-c-or-cpp-language-executables.md)

- [Bestimmen Sie die Exportmethode verwendet werden](../build/determining-which-exporting-method-to-use.md)

- [Importieren Sie in eine Anwendung mithilfe von "__declspec(dllimport)" "](../build/importing-into-an-application-using-declspec-dllimport.md)

- [Initialisieren einer DLL](../build/run-time-library-behavior.md#initializing-a-dll)

### <a name="what-do-you-want-to-know-more-about"></a>Worüber möchten Sie mehr erfahren?

- [Ergänzte Namen](../build/reference/decorated-names.md)

- [Importieren und Exportieren von Inlinefunktionen](../build/importing-and-exporting-inline-functions.md)

- [Gegenseitige Importe](../build/mutual-imports.md)

## <a name="see-also"></a>Siehe auch

[Exportieren aus einer DLL](../build/exporting-from-a-dll.md)

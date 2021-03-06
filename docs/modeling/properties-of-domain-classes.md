---
title: Eigenschaften von Domänenklassen
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- Domain-Specific Language, domain class
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
ms.openlocfilehash: 5d880ac873766c59adfa53e9e61a6ad13520c135
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
ms.locfileid: "31949022"
---
# <a name="properties-of-domain-classes"></a>Eigenschaften von Domänenklassen
Domänenklassen haben die Eigenschaften in der folgenden Tabelle. Informationen zu Domänenklassen finden Sie unter [Grundlegendes zu Modellen, Klassen und Beziehungen](../modeling/understanding-models-classes-and-relationships.md). Weitere Informationen zum Verwenden dieser Eigenschaften finden Sie unter [anpassen und Erweitern einer domänenspezifischen Sprache](../modeling/customizing-and-extending-a-domain-specific-language.md).

|Eigenschaft|Beschreibung|Standard|
|--------------|-----------------|-------------|
|Zugriffsmodifizierer|Die Zugriffsebene der Domänenklasse (`public` oder `internal`).|`public`|
|Benutzerdefinierte Attribute|Verwendet, um den Code Quellklasse Attribute hinzuzufügen, die von dieser Domänenklasse generiert wird.|\<keine >|
|Doppelter generiert abgeleitet|Wenn `True`, eine Basisklasse und eine partielle Klasse (zur Unterstützung von Anpassung außer Kraft) generiert werden. Weitere Informationen finden Sie unter [überschreiben und erweitern die generierte Klassen](../modeling/overriding-and-extending-the-generated-classes.md).|`False`|
|Verfügt über benutzerdefinierte-Konstruktor|Wenn `True`, ein benutzerdefinierter Konstruktor im Quellcode bereitgestellt werden. Weitere Informationen finden Sie unter [überschreiben und erweitern die generierte Klassen](../modeling/overriding-and-extending-the-generated-classes.md).|`False`|
|Inheritance Modifier|Beschreibt die Art der Vererbung von der Quellklasse für Code, der von der Domänenklasse generiert wird (`none`, `abstract` oder `sealed`).|`none`|
|Basisklasse|Wenn diese Domänenklasse abgeleitet ist, den Namen der Basisklasse.|\<keine >|
|name|Der Name dieser Domäne-Klasse.|Aktuelle name|
|Namespace|Der Namespace dieser Domäne-Klasse.|Aktuellen namespace|
|Hinweise|Informelle Hinweise, die mit dieser Domänenklasse verknüpft sind.|\<keine >|
|Beschreibung|Die Beschreibung, die verwendet wird, um die Benutzeroberfläche des Designers generierten zu dokumentieren.|\<keine >|
|Anzeigename|Der Name, der in der generierten Designer für diese Domänenklasse angezeigt wird.|\<keine >|
|Hilfsschlüsselwort|Das optionale Schlüsselwort, das verwendet wird, um die index-F1-Hilfe für diese Domänenklasse.|\<keine >|

## <a name="see-also"></a>Siehe auch

- [Domänenspezifische Sprache Tools Glossar](http://msdn.microsoft.com/ca5e84cb-a315-465c-be24-76aa3df276aa)
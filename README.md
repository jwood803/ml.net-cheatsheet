# ML.NET Cheat Sheet

Quick reference for all the things you can do in ML.NET


## Load Text Data

### Load text with default parameters.
```csharp
var data = new Microsoft.ML.Data.TextLoader(filePath).CreateFrom<SalaryData>();
```

### Load text with different separator/delimeter
```csharp
var data = new Microsoft.ML.Data.TextLoader(filePath).CreateFrom<SalaryData>(separator: ',');
```

### Load text to include the header
```csharp
var data = new Microsoft.ML.Data.TextLoader(filePath).CreateFrom<SalaryData>(useHeader: true);
```

## Cross Validation
### Create cross validator and run validation
```csharp
var crossValidator = new CrossValidator() { Kind = MacroUtilsTrainerKinds.SignatureRegressorTrainer };

var crossValidatorOutput = crossValidator.CrossValidate<SalaryData, SalaryPrediction>(pipeline);
```

### Create cross validator and run with specific number of folds
```csharp
var crossValidator = new CrossValidator() { Kind = MacroUtilsTrainerKinds.SignatureRegressorTrainer, NumFolds = 10 };

var crossValidatorOutput = crossValidator.CrossValidate<SalaryData, SalaryPrediction>(pipeline);
```

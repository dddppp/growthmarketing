function experimentSignupFlow(product) {
    hypothesis = "Reducing signup steps will increase conversions"
    variantA = product.createSignupFlow(steps=3)
    variantB = product.createSignupFlow(steps=1)
    
    runA_B_Test(variantA, variantB)
    
    results = analyzeA_B_TestResults(variantA, variantB)
    
    if results.variantB.conversionRate > results.variantA.conversionRate {
        implementChange(variantB)
        return "Signup flow improved"
    } else {
        return "No significant change"
    }
}

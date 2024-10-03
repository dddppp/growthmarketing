ffunction processGrowthIdeas(ideas, kpis) {
    prioritizedIdeas = prioritizeIdeas(ideas)
    
    for idea in prioritizedIdeas {
        if (isLowEffortHighImpact(idea) && alignsWithKPI(idea, kpis)) {
            experiment = outlineExperiment(idea)
            runExperiment(experiment)
            results = evaluateResults(experiment)
            if (results.success) {
                implementChange(idea)
            } else {
                iterateOnIdea(idea)
            }
        }
    }
    return "Top ideas implemented based on impact"
}

function pirateFunnel(product) {

    // Awareness: Track how many people do you reach 
    awareness = {
        channels: trackReach(product),        //  Track how many people you reach, e.g. via a campaign
    }
    
    // Acquisition: Track how users discover your product
    acquisition = {
        signups: trackVisits(product) | trackDownloads(product)  // Number of users who visit your website or download your app 
    }
    
    // Activation: Track when users experience the core value of the product
    activation = {
        onboarding: trackOnboardingCompletion(product),   // How many users complete onboarding
        featureUse: trackFeatureUse(product),             // How many users use key features
    }
    
    // Retention: Track whether users come back and continue using the product
    retention = {
        weeklyActiveUsers: trackWeeklyActiveUsers(product),  // Users who return weekly
        monthlyActiveUsers: trackMonthlyActiveUsers(product) // Users who return monthly
    }
   
    // Referral: Track how many users refer others to the product
    referral = {
        invitesSent: trackInvitesSent(product),                   // Number of referrals sent by users
        referralsUsed: trackReferralCodeUsage(product)   // Number of referrals redeemed
    }
    
    // Revenue: Track how the product generates revenue from users
    revenue = {
        subscriptions: trackSubscriptionPurchases(product), // Number of paying subscribers
        upsells: trackUpsells(product)                      // Number of users upgrading to higher plans
    }
    
    return {
        awareness: awareness,
        acquisition: acquisition,
        activation: activation,
        retention: retention,
        referral: referral,
        revenue: revenue
    }
}

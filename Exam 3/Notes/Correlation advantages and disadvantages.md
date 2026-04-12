Joint distribution:
		advantages:
			- simplicity and computational efficiency
			- consistency in known theorical framework
			- Avoidance of misuse and specific error
				- less chance to have a black box model
		 disadvantages:
			 - Need to have the same marginal distribution
			 - poor handling of tail dependencies
			 - reliance on linear corelation
 Copula:
		 advantages:
			- Marginal flexibility
			- Capturing tail dependencies
			- Scale invariance 
			- Can build all model first and then focus on joint distribution
		 disadvantages:
			 - Error in initial model estimation can be transferred to the copula part
			 - Black box risk
			 - Difficulty with discrete data
	 
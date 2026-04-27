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
			 -

correlation measure drawbacks:
		- Correlation is a scalar measure of dependency
		- Possible values depend on the marginal distributions
		- Perfectly positive dependent risks don’t necessarily have a correlation of 1
		- A correlation of zero does not indicate independence of risks 
		- Correlation is not invariant under transformations of risks
		- Correlation is only defined when variances of risks are finite
	 
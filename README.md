# Weighted-Sorting-Algorithm-Greedy
=====================================
#                 **** KEY: HOW TO TUNE WEIGHTS *********                                                
#             (This is a limited example to explain tuning)
# ===================================

#                        Transition 1 (A--> B)         Transition 2 (C--> D)
#                        ---------------------         ---------------------
# Flow Rate Diff:        15 lbs/min                    20 lbs/min
#                        (Flow Weight: 5)              (Flow Weight: 5)

# Density Difference:    0.2 LBS/ft^2                  0.6 LBS/ft^2
#                        (Density Weight: 100)         (Density Weight: 100)

# Real Waste:            50 ft^3                       100 ft^3  

# Score Function:
# Score = (Flow Rate * Weight) + (Density Difference * Weight)
# (Adapt to your system, this is just a simplified example)

# =============================================================================
# Round 1: Initial Calculation
# =============================================================================

# Model Score 1 = (15 * 5) + (0.2 * 100) = 95    
# Real Waste 1: 50 ft^3

# Model Score 2 = (20 * 5) + (0.6 * 100) = 160    
# Real Waste 2: 100 ft^3

# ****** Tuning Equation (Ratio of Ratios) ******

#             (Model Ratio: 95 / 160)
#    Result = -----------------------  =  1.1875
#             (Real Ratio:  50 / 100)

# Conclusion: This is close to 1 but not quite 1
#              To get closer to 1, the bottom needs to be bigger

# =============================================================================
# Round 2: Adjustment (Density Weight 100 --> 200)
# =============================================================================

# Model Score 1 = (15 * 5) + (0.2 * 200) = 115
# Real Waste 1: 50 ft^3

# Model Score 2 = (20 * 5) + (0.6 * 200) = 220
# Real Waste 2: 100 ft^3

# ****** Tuning Equation ******

#             (115 / 220)
#    Result = ----------  =  1.045
#             (50 / 100)

# Conclusion:  This is closer to 1, so we are moving in the right direction

# =============================================================================
#                           GOAL: RATIO OF RATIOS = 1                                                
# ****************(For as many different combinations as possible) ***********

#       If this is close to 1 for a bunch of different combinations, 
#    The algorithm will correctly predict waste in reality, and be functional 
# =============================================================================



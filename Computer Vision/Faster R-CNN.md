Insert a Region Proposal Network(RPN) to predict proposal from features.
It trains on 4 losses
- RPN classify object/not object
- Regress Box coordinates
- Final Classification score (object classes)
- Final Box coordinates
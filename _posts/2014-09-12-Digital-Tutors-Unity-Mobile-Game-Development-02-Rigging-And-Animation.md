---
layout : post
category : D Developing Tools
tags : [Unity, Maya, Rigging, Animation]
---
### Rigging Notes 

*  Scene optimization.
*  Bone Limit:30 bones per mesh **safe**.Avoid 80 bones or more.  
(This depends on what will be shown on screen at a time)
*  Max Skin Influence: 4 bones per vertex.
*  Root joint of skeleton at origin of scene.
*  File referencing.

#### scripts
* centerWorldJoint_vert.mel  

		////Create a joint at the center of selected vertices

		//Find selection of componenets
		string $selVert[] = `ls -sl -fl`;
    
	    //Create a cluster
	    string $cl[] = `newCluster " -relative -envelope 1"`;
	    //Create a world joint
	    select -cl;
	    string $jnt = `joint`;
	    //Point Constraint the joint to the cluster
	    string $ptCnsJnt[] = `pointConstraint $cl $jnt`;
	    //Find the Point Constraint
	    string $findPtCns[] = `listRelatives -type pointConstraint $jnt`;
	    //Select and delete the Point Constrain and cluster
	    select $findPtCns[0] $cl[0]; doDelete;
	    //Select the joint
	    select -cl; select $jnt;

---

### Animation Notes
*  What frame rate?  24 25 30 60
*  What animations are needed?  
*  Lock down start & end frames of each sequence with key frames.  
*  Frame document(List of frame durations of animated assets for programmers).  
*  All animations created in one scence file per character.
*  Animation Priciples
*  F-curves should maintain a constant extrapolation (function curves)
*  Strategies for creating animations fast without sacrificing quality. 

 

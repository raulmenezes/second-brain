---
tags:
  - area/devops
  - area/knowledge
  - topic/aws
  - topic/kubernetes
  - topic/snippets
---

# Import { LearningTaskProperties } from '. learning task properties.dto…

import { ObjectiveType } from '../enums/objective-type.enum';
import { EvaluationMetric } from '../enums/evaluation-metric.enum';

export interface XGConfiguration {
  balanceAndSplitRandom: boolean;
  numberOfModelsToBuild: number;
  binaryMetric?: any;
  regressionMetric?: any;
  xgBoostProperty: XGBoostProperty;
}

export interface XGBoostProperty {
  generalParams: GeneralParams;
  lgParams: LGParams;
}

export interface GeneralParams {
  boosterParams: BoosterProperty;
  boosterType: BoosterType;
  numRounds: number;
  verbosity: number;
}

export interface BoosterProperty {
  treeBoosterProperty: any;
  treeBoosterGridProperty: any;
}

export interface LGParams {
  performGridSearch: boolean;
}

export interface XGConfigurationForm {
  balanceAndSplitRandom?: boolean;
  numberOfModelsToBuild: number;
  boosterType: BoosterType;
  performGridSearch: boolean;
  treeBoosterProperties?: TreeBoosterProperties;
  linearBoosterProperties?: LinearBoosterProperties;
  learningTaskProperties: LearningTaskProperties;
}

export interface TreeBoosterProperties {
  max_depth: number | number\[\];
  min_child_weight: number | number\[\];
  eta: number | number\[\];
  subsample: number | number\[\];
  colsample_bytree: number | number\[\];
  // Non-grid-search params
  min_split_loss: number;
  lambda: number;
  alpha: number;
}

export interface LinearBoosterProperties {
  lambda: number | number\[\];
  alpha: number | number\[\];
  // Non-grid-search params
  updater_type: UpdaterType;
  feature_selector: FeatureSelector;
  top_k: number;
}

export enum UpdaterType {
  SHOTGUN = 'SHOTGUN',
  COOR_DESCEUT = 'COOR_DESCEUT'
}

export enum FeatureSelector {
  CYCLE = 'CYCLE',
  SHUFFLE = 'SHUFFLE',
  RANDOM = 'RANDOM',
  GREEDY = 'GREEDY',
  THRIFTY = 'THRIFTY',
}

export enum BoosterType {
  TREE = 'TREE',
  LINEAR = 'LINEAR',
  DART = 'DART'
}

export const DEFAULT_XG_CONGIF: XGConfigurationForm = {
  numberOfModelsToBuild: 1,
  boosterType: BoosterType.TREE,
  performGridSearch: false,
  treeBoosterProperties: {
    max_depth: 2,
    min_child_weight: 10,
    eta: 0.3,
    subsample: 0.7,
    colsample_bytree: 0.7,
    // Non-grid-search params
    min_split_loss: 0.0,
    lambda: 1.0,
    alpha: 0.1,
  },
  linearBoosterProperties: {
    lambda: 0.1,
    alpha: 0.11,
    // Non-grid-search params
    updater_type: UpdaterType.SHOTGUN,
    feature_selector: FeatureSelector.CYCLE,
    top_k: 0,
  },
  learningTaskProperties: {
    objectiveType: ObjectiveType.SQUARE_ERROR,
    squaredLogError: -1,
    variancePower: 1.5,
    baseScore: 0.5,
    evaluationMetric: EvaluationMetric.RMSE,
    errorAt: 0.5
  }
};

## Related
- [[devops-moc]]
- [[sns-simple-notification-service]]
- [[s3-simple-storage-service]]
- [[aws-cloud-practitioner]]
